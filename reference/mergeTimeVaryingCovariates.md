# Merge time-varying covariates into a single data frame. This last data frame will be merged afterwards with all treatment and observation rows.

Merge time-varying covariates into a single data frame. This last data
frame will be merged afterwards with all treatment and observation rows.

## Usage

``` r
mergeTimeVaryingCovariates(covariates, ids_within_arm, arm_offset)
```

## Arguments

- covariates:

  covariates, only time-varying covariates will be extracted

- ids_within_arm:

  ids within the current arm being sampled

- arm_offset:

  arm offset (in term of ID's)

## Value

a data.frame
