# Compute the prediction interval summary over time (deprecated).

Compute the prediction interval summary over time (deprecated).

## Usage

``` r
PI(x, variable, strata = get_default_strata(), level = 0.9)
```

## Arguments

- x:

  data frame

- variable:

  variable(s) used to compute the prediction interval, character vector.
  When more than one variable is supplied, a `variable` column is added
  to the output to identify each one.

- strata:

  named vector with the strata to use, default is c(SCENARIO="all",
  ARM="all"). Only columns that are actually present in `x` are used.

- level:

  PI level, default is 0.9 (90% PI)

## Value

a summary table
