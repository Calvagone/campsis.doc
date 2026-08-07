# Make the VPC summary. Input data frame must contain the following columns: - replicate: replicate number - low: low percentile value in replicate (and in scenario if present) - med: median value in replicate (and in scenario if present) - up: up percentile value in replicate (and in scenario if present) - any scenario column

Make the VPC summary. Input data frame must contain the following
columns: - replicate: replicate number - low: low percentile value in
replicate (and in scenario if present) - med: median value in replicate
(and in scenario if present) - up: up percentile value in replicate (and
in scenario if present) - any scenario column

## Usage

``` r
make_vpc_summary(x, strata = NULL, level = 0.9)
```

## Arguments

- x:

  data frame, with metric

- strata:

  named vector with the strata to use, default is c(SCENARIO="all",
  ARM="all"). Only columns that are actually present in `x` are used.

- level:

  PI level, default is 0.9 (90% PI)

## Value

VPC summary with columns TIME, stratification variables and all
combinations of low, med, up (i.e. low_low, low_med, low_up, etc.)
