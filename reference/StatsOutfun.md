# Create a statistics output function

Create a statistics output function

## Usage

``` r
StatsOutfun(
  variable,
  strata = get_default_strata(),
  stats = c("p5", "median", "p95"),
  name = sprintf("stats_%s", paste0(variable, collapse = "_"))
)
```

## Arguments

- variable:

  variable(s) used to compute the statistics, character vector

- strata:

  named vector with the strata to use, default is c(SCENARIO="all",
  ARM="all")

- stats:

  character vector of statistics to compute. Supported: "median",
  "mean", or percentiles like "p5", "p95", "p2.5", "p97.5". Default is
  c("p5", "median", "p95").

- name:

  name of the output function. Default is 'stats\_\<variable\>'.

## Value

a stats_outfun object
