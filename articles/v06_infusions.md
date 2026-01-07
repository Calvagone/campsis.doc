# Infusions

There are 2 ways to implement infusions in CAMPSIS:

- in the model: infusion duration or rate is defined for each
  compartment
- in the dataset: infusion duration or rate is defined for infusion

In the first case, the simulation engine will take care of the infusion
duration or rate (RATE in dataset will be -1 or -2). In the second case,
CAMPSIS will inject specific values in the RATE column of the dataset.

### Infusion duration or rate implemented in model

Let’s use a 2-compartment model without absorption compartment to
illustrate how this can be achieved.

``` r
model <- model_suite$nonmem$advan3_trans4
```

For this example, we’re going to define a lag time `D1` for this
absorption compartment.

First let’s create a new parameter `D1`, log-normally distributed with a
median of 5 hours and 20% CV.

``` r
model <- model %>% add(Theta(name="D1", value=5))
model <- model %>% add(Omega(name="D1", value=20, type="cv%"))
```

Now, let’s add an equation to the drug model to define `D1`.

``` r
model <- model %>% add(Equation("D1", "THETA_D1*exp(ETA_D1)"))
```

Finally, we need to tell CAMPSIS that `D1` corresponds the infusion
duration for the first compartment.

``` r
model <- model %>% add(InfusionDuration(compartment=1, rhs="D1"))
```

Our persisted drug model would look like this:

``` r
model
```

    ## [MAIN]
    ## CL=THETA_CL*exp(ETA_CL)
    ## V1=THETA_V1*exp(ETA_V1)
    ## V2=THETA_V2*exp(ETA_V2)
    ## Q=THETA_Q*exp(ETA_Q)
    ## S1=V1
    ## D1=THETA_D1*exp(ETA_D1)
    ## 
    ## [ODE]
    ## d/dt(A_CENTRAL)=Q*A_PERIPHERAL/V2 + (-CL/V1 - Q/V1)*A_CENTRAL
    ## d/dt(A_PERIPHERAL)=-Q*A_PERIPHERAL/V2 + Q*A_CENTRAL/V1
    ## d/dt(A_OUTPUT)=CL*A_CENTRAL/V1
    ## F=A_CENTRAL/S1
    ## 
    ## [DURATION]
    ## A_CENTRAL=D1
    ## 
    ## [ERROR]
    ## CONC=F
    ## CONC_ERR=CONC*(EPS_PROP + 1)
    ## 
    ## 
    ## THETA's:
    ##   name index value   fix
    ## 1   CL     1     5 FALSE
    ## 2   V1     2    80 FALSE
    ## 3   V2     3    20 FALSE
    ## 4    Q     4     4 FALSE
    ## 5   D1     5     5 FALSE
    ## OMEGA's:
    ##   name index index2  value   fix type
    ## 1   CL     1      1  0.025 FALSE  var
    ## 2   V1     2      2  0.025 FALSE  var
    ## 3   V2     3      3  0.025 FALSE  var
    ## 4    Q     4      4  0.025 FALSE  var
    ## 5   D1     5      5 20.000 FALSE  cv%
    ## SIGMA's:
    ##   name index index2 value   fix type
    ## 1 PROP     1      1 0.025 FALSE  var
    ## No variance-covariance matrix
    ## 
    ## Compartments:
    ## A_CENTRAL (CMT=1)
    ## A_PERIPHERAL (CMT=2)
    ## A_OUTPUT (CMT=3)

Now, let’s infuse 1000 mg and run the simulation.

``` r
ds1 <- Dataset(50) %>% 
  add(Infusion(time=0, amount=1000)) %>%
  add(Observations(times=seq(0,24,by=0.5)))
```

``` r
results_d1 <- model %>% simulate(dataset=ds1, seed=1)
shadedPlot(results_d1, "CONC")
```

![](v06_infusions_files/figure-html/infusion_model%20-1.png)

### Infusion duration or rate implemented in dataset

The same simulation can be performed by defining the infusion duration
in the dataset.

For this, we need to sample `D1` values. This can be done as follows:

``` r
distribution <- ParameterDistribution(model=model, theta="D1", omega="D1") %>%
  sample(50L)
```

We can then pass the pre-sampled distribution.

``` r
ds2 <- Dataset(50) %>%
  add(Infusion(time=0, amount=1000, duration=distribution)) %>%
  add(Observations(times=seq(0,24,by=0.5)))
```

Here is an overview of the dataset in its table form if we filter on the
doses:

``` r
ds2 %>% export(dest="RxODE") %>% dosingOnly() %>% head()
```

    ## # A tibble: 6 × 9
    ##      ID   ARM  TIME  EVID   MDV   AMT CMT    RATE DOSENO
    ##   <dbl> <int> <dbl> <int> <int> <dbl> <chr> <dbl>  <int>
    ## 1     1     0     0     1     1  1000 1      226.      1
    ## 2     2     0     0     1     1  1000 1      193.      1
    ## 3     3     0     0     1     1  1000 1      236.      1
    ## 4     4     0     0     1     1  1000 1      146.      1
    ## 5     5     0     0     1     1  1000 1      187.      1
    ## 6     6     0     0     1     1  1000 1      235.      1

Let’s now simulate this dataset using the original model.

``` r
results_d1 <- model_suite$nonmem$advan4_trans4 %>% simulate(dataset=ds2, seed=1)
shadedPlot(results_d1, "CONC")
```

![](v06_infusions_files/figure-html/infusion_dataset%20-1.png)
