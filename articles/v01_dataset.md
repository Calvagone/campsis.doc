# Create your dataset

### Instantiate a dataset

Create a dataset of 3 subjects:

``` r
ds <- Dataset(subjects=3)
```

Or shortly:

``` r
ds <- Dataset(3)
```

Check how many subjects are part of this dataset:

``` r
ds %>% length()
```

    ## [1] 3

See all methods that can be applied on a dataset:

``` r
methods(class=class(ds))
```

    ##  [1] add                      applyAction              contains                
    ##  [4] delete                   export                   find                    
    ##  [7] getCovariates            getEventCovariates       getFixedCovariates      
    ## [10] getIOVs                  getOccasions             getTimes                
    ## [13] getTimeVaryingCovariates length                   loadFromJSON            
    ## [16] replace                  setLabel                 setSubjects             
    ## [19] show                     simulate                 unwrapTreatment         
    ## [22] updateADDL               updateAmount             updateII                
    ## [25] updateRepeat            
    ## see '?methods' for accessing help and source code

Oh, this looks cool. There are plenty of functions to play with.  
These functions will be illustrated little by little in the other
vignettes.

In the next sections below, we’ll see how we can add boluses and
infusions:

### Add a bolus

A bolus can be created using the constructor `Bolus` and added to the
dataset:

``` r
ds <- ds %>% add(Bolus(time=0, amount=1000))
```

By default, it will be injected into the first compartment (CMT=1). If
another compartment needs to be used, the `compartment` argument may be
used as follows:

``` r
Bolus(time=0, amount=1000, compartment=2)
```

Bioavailabilities (`f` argument) and lag times (`lag` argument) can be
implemented as well, in the dataset. This will be illustrated in other
vignettes.

### Add an infusion

An infusion can be created using the constructor `Infusion` and added to
the dataset:

``` r
ds <- ds %>% add(Infusion(time=0.5, amount=1000))
```

As previously, the default compartment is the first compartment.

Infusion rate (`rate` argument) or duration (`duration` argument),
bioavailabilities (`f` argument) and lag times (`lag` argument) can be
implemented as well, in the dataset. This will be illustrated in other
vignettes.

### Add observations

Observations can be created using the constructor `Observations` and
added to the dataset:

``` r
ds <- ds %>% add(Observations(times=c(0.5, 1)))
```

The default compartment is the first one. Although the compartment
number is not useful for simulations (as simulation engines are able to
look at all `DV` at once), it can still be useful when exporting a table
for a modeling tool.

### Export dataset

So far so good! The dataset contains 5 subjects, 1 bolus and 1 infusion.
We are going to export it to a 2-dimensional table. This step is
implicitly done by CAMPSIS when you simulate your model.

``` r
table <- ds %>% export(dest="RxODE")
table
```

    ## # A tibble: 12 × 9
    ##       ID   ARM  TIME  EVID   MDV   AMT CMT    RATE DOSENO
    ##    <dbl> <int> <dbl> <int> <int> <dbl> <chr> <dbl>  <int>
    ##  1     1     0   0       1     1  1000 1         0      1
    ##  2     1     0   0.5     0     0    NA 1         0     NA
    ##  3     1     0   0.5     1     1  1000 1        NA      2
    ##  4     1     0   1       0     0    NA 1         0     NA
    ##  5     2     0   0       1     1  1000 1         0      1
    ##  6     2     0   0.5     0     0    NA 1         0     NA
    ##  7     2     0   0.5     1     1  1000 1        NA      2
    ##  8     2     0   1       0     0    NA 1         0     NA
    ##  9     3     0   0       1     1  1000 1         0      1
    ## 10     3     0   0.5     0     0    NA 1         0     NA
    ## 11     3     0   0.5     1     1  1000 1        NA      2
    ## 12     3     0   1       0     0    NA 1         0     NA

A few explanations need to be given here regarding the following column
names:

- ID: this is the subject ID, it always starts at 1. ID’s are
  consecutive in CAMPSIS
- ARM: this is the ARM number. 0 is the default arm.
- RATE: the RATE column (0 for boluses, -1/-2 for a rate/infusion
  defined in the model, NA when no information is available)
- DOSENO: the dose number. Doses (boluses and infusions) are numbered
  according to the time they occur.

### Add several arms

Instead of using the default arm (0) in the dataset, several arms can be
created and added to the dataset. These arms are independent in the
sense the treatment(s) and the observation(s) can be totally different.

To illustrate this, let’s create a dataset with two arms.

``` r
arm1 <- Arm(subjects=2)
arm2 <- Arm(subjects=3)
```

Let’s create 2 different treatments:

``` r
arm1 <- arm1 %>% add(Bolus(time=0, amount=1000))
arm2 <- arm2 %>% add(Bolus(time=0, amount=2000))
```

Observations may also differ:

``` r
arm1 <- arm1 %>% add(Observations(times=c(0.5, 1)))
arm2 <- arm2 %>% add(Observations(times=c(1, 1.5)))
```

Let’s now add these 2 arms into a fresh dataset:

``` r
ds <- Dataset() %>% add(c(arm1, arm2))
```

We can check how many subjects are part of this dataset:

``` r
ds %>% length()
```

    ## [1] 5

The resulting exported table is as follows:

``` r
table <- ds %>% export(dest="RxODE")
table
```

    ## # A tibble: 15 × 9
    ##       ID   ARM  TIME  EVID   MDV   AMT CMT    RATE DOSENO
    ##    <dbl> <int> <dbl> <int> <int> <dbl> <chr> <dbl>  <int>
    ##  1     1     1   0       1     1  1000 1         0      1
    ##  2     1     1   0.5     0     0    NA 1         0     NA
    ##  3     1     1   1       0     0    NA 1         0     NA
    ##  4     2     1   0       1     1  1000 1         0      1
    ##  5     2     1   0.5     0     0    NA 1         0     NA
    ##  6     2     1   1       0     0    NA 1         0     NA
    ##  7     3     2   0       1     1  2000 1         0      1
    ##  8     3     2   1       0     0    NA 1         0     NA
    ##  9     3     2   1.5     0     0    NA 1         0     NA
    ## 10     4     2   0       1     1  2000 1         0      1
    ## 11     4     2   1       0     0    NA 1         0     NA
    ## 12     4     2   1.5     0     0    NA 1         0     NA
    ## 13     5     2   0       1     1  2000 1         0      1
    ## 14     5     2   1       0     0    NA 1         0     NA
    ## 15     5     2   1.5     0     0    NA 1         0     NA
