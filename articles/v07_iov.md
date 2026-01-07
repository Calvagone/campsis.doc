# Inter-occasion variability

This vignette shows how inter-occasion variability (IOV) can be added on
a parameter at each administration.

### Treatment IOV on KA

Let’s use a 2-compartment model with absorption compartment for this
example.

``` r
model <- model_suite$nonmem$advan4_trans4
```

We’re going to add a term `IOV_KA` on parameter `KA`. This can be done
as follows:

``` r
model <- model %>% replace(Equation("KA", "THETA_KA*exp(ETA_KA + IOV_KA)"))
```

This model will not run unless we give some values for `IOV_KA`. This
can achieved by adding IOV to the dataset. The following code will
create a simple dataset with IOV.

``` r
ds_iov <- Dataset(50) %>% 
  add(Bolus(time=c(0,24,48), amount=1000, compartment=1)) %>% 
  add(Observations(times=seq(0,72, by=0.5))) %>% 
  add(IOV("IOV_KA", distribution=NormalDistribution(mean=0, sd=1)))
```

To disable IOV on KA, the `replace` method can be used:

``` r
ds_no_iov <- ds_iov %>% replace(IOV("IOV_KA", 0))
```

We can now run the model with IOV on `KA` and without.

``` r
results_iov <- model %>% simulate(dataset=ds_iov, seed=1)
results_no_iov <- model %>% simulate(dataset=ds_no_iov, seed=1)
gridExtra::grid.arrange(shadedPlot(results_iov, "CONC"), shadedPlot(results_no_iov, "CONC"), nrow=1)
```

![](v07_iov_files/figure-html/lag_time_model%20-1.png)
