# Compute generic statistics over time.

Compute generic statistics over time.

## Usage

``` r
compute_stats(
  x,
  variable,
  strata = get_default_strata(),
  stats = c("p5", "median", "p95")
)
```

## Arguments

- x:

  data frame

- variable:

  variable(s) used to compute the statistics, character vector.

- strata:

  named vector with the strata to use, default is c(SCENARIO="all",
  ARM="all").

- stats:

  character vector of statistics to compute. Supported: "median",
  "mean", or percentiles like "p5", "p95", "p2.5", "p97.5".

## Value

a summary table in long format
