# Run your simulation in parallel

This vignette explains how Campsis can benefit from several CPU cores
for running your simulation efficiently.

### Base model and dataset

``` r

model <- model_suite$pk$`2cpt_fo_mm`

dataset <- Dataset(1000) %>%
  add(Bolus(time = 0, amount = 100, ii = 12, addl = 10)) %>%
  add(Observations(times = 0:(11 * 12)))
```

### Run replicates in parallel

Sequential run:

``` r

tic()
results <- simulate(
  model = model,
  dataset = dataset,
  dest = "mrgsolve",
  seed = 1,
  outfun = PIOutfun(variable = "CONC"),
  replicates = 100
)
toc()
```

    ## 146.73 sec elapsed

Using 6 cores:

``` r

settings <- Settings(Hardware(cpu = 6, replicate_parallel = TRUE))
```

``` r

tic()
results <- simulate(
  model = model,
  dataset = dataset,
  dest = "mrgsolve",
  seed = 1,
  outfun = PIOutfun(variable = "CONC"),
  replicates = 100,
  settings = settings
)
toc()
```

    ## 70.99 sec elapsed

``` r

vpc_plot(results)
```

![](v17_run_simulation_in_parallel_files/figure-html/replicates_in_parallel-1.png)

Since there is no uncertainty on the parameters and since 1000 patients
are simulated in each replicate, the confidence intervals on the
percentiles are very low.

### Run scenarios in parallel

Instead of giving a fixed dose, let’s make the dose dynamic using a
`DOSE` covariate:

``` r

dataset_ <- dataset %>%
  add(Covariate("DOSE", 0)) %>%
  add(DoseAdaptation("DOSE"))
```

Let’s create one scenario per dose to be tested:

``` r

scenarios <- Scenarios()
for (dose in c(0.5, 1, 5, 10, 50, 100, 500, 1000, 5000, 10000, 50000, 100000)) {
  scenarios <- scenarios %>%
    add(Scenario(
      name = paste0("DOSE=", dose),
      dataset = dataset_ %>% replace(Covariate("DOSE", dose))
    ))
}
```

Sequential run:

``` r

tic()
results <- simulate(
  model = model,
  dataset = dataset_,
  seed = 1,
  scenarios = scenarios
)
toc()
```

    ## 22.44 sec elapsed

Using 6 cores (auto-setup plan):

``` r

settings <- Settings(Hardware(cpu = 6, scenario_parallel = TRUE))
```

``` r

tic()
results <- simulate(
  model = model,
  dataset = dataset_,
  seed = 1,
  scenarios = scenarios,
  settings = settings
)
toc()
```

    ## 19.83 sec elapsed

Using 6 cores (plan already setup from last execution):

``` r

settings <- Settings(Hardware(
  cpu = 6,
  scenario_parallel = TRUE,
  auto_setup_plan = FALSE
))
```

``` r

tic()
results <- simulate(
  model = model,
  dataset = dataset_,
  seed = 1,
  scenarios = scenarios,
  settings = settings
)
toc()
```

    ## 18.51 sec elapsed

Plot results:

``` r

# Re-arrange scenarios by natural order
results <- results %>%
  mutate(SCENARIO = factor(SCENARIO, levels = unique(SCENARIO)))

shaded_plot(results, "CONC") +
  facet_wrap(~SCENARIO, ncol = 4, scales = "free_y") +
  guides(colour = "none", fill = "none")
```

![](v17_run_simulation_in_parallel_files/figure-html/scenarios_in_parallel-1.png)

### Run slices in parallel

It may be useful to simulate slices in parallel when the simulation time
per individual is high (e.g. long simulation). To illustrate this topic,
let’s dose and observe a drug over a 6-month period.

``` r

dataset_ <- Dataset(200) %>%
  add(Bolus(time = 0, amount = 100, ii = 12, addl = 364)) %>%
  add(Observations(times = 0:(365 * 12)))
```

Sequential run:

``` r

tic()
results <- simulate(
  model = model,
  dataset = dataset_,
  seed = 1
)
toc()
```

    ## 8.9 sec elapsed

Using 6 cores (auto-setup plan):

``` r

settings <- Settings(Hardware(cpu = 6, slice_parallel = TRUE))
```

``` r

tic()
results <- simulate(
  model = model,
  dataset = dataset_,
  seed = 1,
  settings = settings
)
toc()
```

    ## 7.97 sec elapsed

Please note that the default slice size for `mrgsolve` is 500, which
means that only 1 core was used in the previous example. For `rxode2`,
which works with a much smaller slice size of 6 subjects, paralleling
slices may be interesting for long simulations, as demonstrated here.

### Setup plan with package future

As you may have seen in the examples above, the argument
`auto_setup_plan` is `TRUE` by default. This means, that Campsis, will
setup your hardware plan every time you call the `simulate` method. This
comes at a high cost since the setup phase can take some time.

For repeated simulations, it may be useful to setup your plan manually
once for all. To do so, you can call `setup_plan_default` on your
settings or hardware object:

``` r

settings <- Settings(Hardware(
  cpu = 2,
  replicate_parallel = TRUE,
  auto_setup_plan = FALSE
))
setup_plan_default(settings)
```

If you do so, please don’t forget to set the argument `auto_setup_plan`
to FALSE, when you give these settings to the `simulate` method,
otherwise your plan is setup again…

For going back to the sequential execution (1 CPU core), you can call:

``` r

setup_plan_sequential()
```

### Run Campsis in parallel within the pipeline tool targets

The [targets](https://books.ropensci.org/targets/) package is a
Make-like pipeline tool for Statistics and data science in R. With
targets, you can maintain a reproducible workflow without repeating
yourself. It is the ideal pipeline tool to use for medium to large
simulation projects with Campsis.

This package supports parallelisation and therefore can complete your
simulation workflow faster. The following script (`_targets.R`) gives
you a brief overview of how you can run several simulation targets in
parallel.

``` r

library(targets)

source("R/my_script.R")

# Packages loaded by targets
packages <- c("campsis", "progressr", "future")
tar_option_set(packages = packages, storage = "worker", retrieval = "worker")

# Prepare 3 workers
future::plan(future::multisession, workers = 3)

list(
  tar_target(
    model,
    model_suite$pk$`1cpt_zo_abs_lag`,
    deployment = "main"
  ),
  tar_target(
    dataset,
    make_dataset(subjects = 1000, dose = 1000),
    deployment = "main"
  ),
  tar_target(
    results1,
    run_simulation(model = model, dataset = dataset, replicates = 10, seed = 1),
    deployment = "worker"
  ),
  tar_target(
    results2,
    run_simulation(model = model, dataset = dataset, replicates = 10, seed = 2),
    deployment = "worker"
  ),
  tar_target(
    results3,
    run_simulation(model = model, dataset = dataset, replicates = 10, seed = 3),
    deployment = "worker"
  )
)
```

This small project can be downloaded by clicking the link below.

[Download targets
squeletton](data:application/zip;base64,UEsDBAoAAAAAAOCK8FwAAAAAAAAAAAAAAAACAAAAUi9QSwMEFAACAAgAzXH9XJCOv+IMAQAAEQIAAA0AAABSL215X3NjcmlwdC5SXZDPTsMwDMbvlfoO1qRJLSrSQAgujBMXTjxClTXeCORPiZNxQLw7TpO2jFPin+3P9mfEB/ZSBEEY4PEajtEOQTnbUDy84xCoA+kIW/iuK4A/hc/5u9TBHuZvC9unbSoHEFI2L/YYKUlmBBCUQS7fdTMQxkUbGKVRCx2cGYUPBqfUzcKV4vD2bu2WUjO5z3H7b/rrgdCfRbqJGsLPZtfBA1yxQNu2qcxjiN425TRGP3VVVz7anpSJeuq8cMY4ibqbvehYYNRqEAHZK0KUadnil0eKmr3h9i8V3vrRuxMzXiRLY/FkkuS+LJ3Z7PV+mVQ4UoIb40/k9Bk3hZfR6SlkXYz5GqTkxelly3z6L1BLAwQUAAIACADLcf1cOGBaVVIBAAChAwAACgAAAF90YXJnZXRzLlKtks1ugzAMx+9IvEPEeqAS29pyq7Z3mPoCqQEPZQQSxWETe/o5QKYeKlXaKnHwR/z3zzZaVQ7clHtwLXrapkmakBldjXl2eu4nSbVT1j+dsjn1IN6g7qBFEtpAg42oJrHWpomNuZdHUedZDb0lRVkhMutM65DIBed99KPDIMiV0livzCAJff5b/yqiWQjyxrHFsezLuA6DhEPvFH6CvohGPocWHIpSLHHGWvodj1bDkEenH7VXxEjcvIhvWa6cdbQin6eJCLPJZb7ZFaI3DeriwpY0Ko8b223O+9p6+W0kVCQ1tOf1WYNWm6nHwQfcHtSQhcS2uNqgAQ+8jNgCOpRrKKex+sDaB8z9brcrRGMIV2f7p2Z8E94D7ddiN/IhFK8Gwk3yeT6WWWaOZByIjFxvtarB48LE10L+J9i8jrOe6jbQ4d5Ah38ClfcGKm8DpQl/P1BLAQIeAwoAAAAAAOCK8FwAAAAAAAAAAAAAAAACAAAAAAAAAAAAEADtQQAAAABSL1BLAQIeAxQAAgAIAM1x/VyQjr/iDAEAABECAAANAAAAAAAAAAEAAACkgSAAAABSL215X3NjcmlwdC5SUEsBAh4DFAACAAgAy3H9XDhgWlVSAQAAoQMAAAoAAAAAAAAAAQAAAKSBVwEAAF90YXJnZXRzLlJQSwUGAAAAAAMAAwCjAAAA0QIAAAAA)

To run this project, nothing is easier. Open an R console within your
targets folder and type:

``` r

library(targets)
tar_make_future(workers = 3)
```
