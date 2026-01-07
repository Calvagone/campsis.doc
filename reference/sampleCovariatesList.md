# Sample covariates list.

Sample covariates list.

## Usage

``` r
sampleCovariatesList(covariates, ids_within_arm, subset)
```

## Arguments

- covariates:

  list of covariates to sample

- ids_within_arm:

  ids within the current arm being sampled

- subset:

  take subset of original values because export is parallelised

## Value

a dataframe of n rows, 1 column per covariate
