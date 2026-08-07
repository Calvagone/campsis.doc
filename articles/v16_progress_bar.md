# Progress bar

This vignette explains how you can track the simulation progress thanks
to the package `progressr`.

### Track the simulation progress in an R script

Load package `progressr` as follows:

``` r

library(progressr)
```

The easiest way to track the progress is to add the following snippet
once for all in your script. By doing so, any call to the simulate
method of `campsis` will display the progress bar.

``` r

handlers(global = TRUE)
```

By default, the progress bar will only give the progress as a
percentage. Any user-custom handler may be provided. Please have a look
at the official
[documentation](https://CRAN.R-project.org/package=progressr) (Vignette
`progressr`: An Introduction / ‘Customizing how progress is reported’).

If you want to use the default handler from `campsis`, which gives you
more details about what’s being simulated and what’s the remaining time
(ETA), you can write:

``` r

handlers(campsis_handler())
```

If you don’t want your handler(s) to be global, you can also explicitly
call the method `with_progress`. The snippet below is an example of
simulation where this method is called.

``` r

dataset <- Dataset(1000) %>%
  add(Infusion(time = 0, amount = 1000, compartment = 1, ii = 24, addl = 6)) %>%
  add(Observations(seq(0, 7 * 24)))

model <- model_suite$pk$`1cpt_fo`
results <- with_progress(simulate(
  model = model,
  dataset = dataset,
  dest = "mrgsolve",
  seed = 1,
  replicates = 3
))
shadedPlot(results, "CONC", "replicate")
```

![](v16_progress_bar_files/figure-html/with_progress_example-1.png)

Any handler may be provided as well:

``` r

results <- with_progress(
  simulate(
    model = model,
    dataset = dataset,
    dest = "mrgsolve",
    seed = 1,
    replicates = 3
  ),
  handlers = campsis_handler()
)
```

### Track the simulation progress in a targets project

The [targets](https://books.ropensci.org/targets/) package is a
Make-like pipeline tool for Statistics and data science in R. With
targets, you can maintain a reproducible workflow without repeating
yourself. It is the ideal pipeline tool to use for medium to large
simulation projects with Campsis.

The following script (`_targets.R`) gives you a brief overview of what
you can achieve with targets and how the progress bar can be enabled. It
is important to mention that `handlers(global=TRUE)` can’t be used in
such a script. If you try to do so, an error message will pop up.

``` r

library(targets)

source("R/my_script.R")

# Packages loaded by targets
packages <- c("campsis", "progressr")
tar_option_set(packages = packages)

# Enable progress bar
options(progressr.enable = TRUE)
progressr::handlers(campsis::campsis_handler())

list(
  tar_target(
    model,
    model_suite$pk$`1cpt_fo`
  ),
  tar_target(
    dataset,
    make_dataset(subjects = 1000, dose = 1000)
  ),
  tar_target(
    results,
    run_simulation(model = model, dataset = dataset, replicates = 3)
  )
)
```

The R folder contains as much as possible of the code (or logic) being
executed, in the form of R functions. The snippet below shows the
content of `my_script.R`. An explicit call to `with_progress` will make
the progress bar appear when executing the target `results`.

``` r

make_dataset <- function(subjects, dose) {
  dataset <- Dataset(subjects = subjects) %>%
    add(Infusion(
      time = 0,
      amount = dose,
      compartment = 1,
      ii = 24,
      addl = 6
    )) %>%
    add(Observations(seq(0, 7 * 24)))
  return(dataset)
}

run_simulation <- function(model, dataset, replicates) {
  results <- with_progress(simulate(
    model = model,
    dataset = dataset,
    dest = "mrgsolve",
    seed = 1,
    replicates = replicates
  ))
  return(results)
}
```

This small project can be downloaded by clicking the link below.

[Download targets
squeletton](data:application/zip;base64,UEsDBAoAAAAAAOCK8FwAAAAAAAAAAAAAAAACAAAAUi9QSwMEFAACAAgA0XH9XASvnuMHAQAABAIAAA0AAABSL215X3NjcmlwdC5SXZDPTsMwDMbvk/oO1qRJLSrSQAgujBMXTjxClTXeyMifEifjgHh3nCZtN27xL58/258Rn9hJEQRhgOdbOETbB+VsTXF/wj5QC9IRNvBTrQAuhK/5OetgB9Ozgc3LJskBhJT1mz1ESpYZAQRlkOXbdgLCuGgDozRqpr0zg/DB4Ph1N3OluLx/WLql1Ewec938m/6+J/RnkW6imvCr3rbwBDds0DRNknkM0du6nMbot1pVKx9tR8pEPXZeJWOcRN1OWbRsMGjVi4BUUvJIUXMi3PStwkc3eHdkxuOzIZYkRiPePBtmNiW8m/0LR0pwbfyRnD7junBClBfpLLswXIr0eXVtWTFf+wdQSwMEFAACAAgACXP9XFSsIrsdAQAAEwIAAAoAAABfdGFyZ2V0cy5SfVCxboMwEN2R+IcTzWAkmibqhpoxe4Xa2TnMibgxseUzA/36GjBRh6qSh/O9e+/eO6Nbj34SAX1Pgcs8yzO2o1ckiuZlmCQrr13YN8UCPcE7qhv2xGAsdtRBO0Hi5pnbsLdnUKJQODjWXFRQOG97T8x+lonz0rqg7V0yBfFgnWAr067zHVtDsJGhRZ9nK5PFQ3JP69gJPprPc6Q+kLq+4r0z5FkkL3WdCpkQUS67jOYg8gzmLHLNs3wBBtuRqX7VkkcdaOduu8tRuSC/rcSWpcH+Mk+V1Z8yHQaMYTchvJFMLcFj+0UqzPmPh8Ohgs4ypU/5j2SMOJrASdKP8Zp6GA3O5xGL1Siy2t/Wx8ZmJNKd0QrDcvjXdVGexfcDUEsBAh4DCgAAAAAA4IrwXAAAAAAAAAAAAAAAAAIAAAAAAAAAAAAQAO1BAAAAAFIvUEsBAh4DFAACAAgA0XH9XASvnuMHAQAABAIAAA0AAAAAAAAAAQAAAKSBIAAAAFIvbXlfc2NyaXB0LlJQSwECHgMUAAIACAAJc/1cVKwiux0BAAATAgAACgAAAAAAAAABAAAApIFSAQAAX3RhcmdldHMuUlBLBQYAAAAAAwADAKMAAACXAgAAAAA=)

To run this project, simply open an R console within your targets folder
and type:

``` r

library(targets)
tar_make()
```
