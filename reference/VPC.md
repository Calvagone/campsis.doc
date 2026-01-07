# Compute the VPC summary. Input data frame must contain the following columns: - replicate: replicate number - low: low percentile value in replicate (and in scenario if present) - med: median value in replicate (and in scenario if present) - up: up percentile value in replicate (and in scenario if present) - any scenario column

Compute the VPC summary. Input data frame must contain the following
columns: - replicate: replicate number - low: low percentile value in
replicate (and in scenario if present) - med: median value in replicate
(and in scenario if present) - up: up percentile value in replicate (and
in scenario if present) - any scenario column

## Usage

``` r
VPC(x, scenarios = NULL, level = 0.9)
```

## Arguments

- x:

  data frame

- scenarios:

  scenarios, character vector, NULL is default

- level:

  PI level, default is 0.9 (90% PI)

## Value

VPC summary with columns TIME, \<scenarios\> and all combinations of
low, med, up (i.e. low_low, low_med, low_up, etc.)
