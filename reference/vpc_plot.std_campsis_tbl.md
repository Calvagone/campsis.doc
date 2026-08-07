# VPC plot for standard Campsis simulation output.

Plots VPC ribbons (a confidence interval around the median, lower and
upper percentiles) from a `std_campsis_tbl`, i.e. the default output of
[`simulate()`](https://calvagone.github.io/campsis.doc/reference/simulate.md)
with multiple replicates and no custom `outfun`
([`DefaultOutfun`](https://calvagone.github.io/campsis.doc/reference/DefaultOutfun.md)).
In this case the data contains all unsummarised individual profiles, so
the per-replicate prediction interval is computed first (the
lower/median/upper percentiles of `variable` across individuals within
each replicate), before the confidence interval around each percentile
is computed across replicates.

## Usage

``` r
# S3 method for class 'std_campsis_tbl'
vpc_plot(
  x,
  variable = "CONC",
  strata = "auto",
  pi_level = 0.9,
  ci_level = 0.9,
  alpha = 0.15,
  facet = TRUE,
  ...
)
```

## Arguments

- x:

  a `std_campsis_tbl` object with a `replicate` column

- variable:

  name of the column to summarise on the y-axis. Defaults to `"CONC"`.
  An informative error is raised when the column is absent.

- strata:

  stratification for the VPC. One of `"auto"`, `NULL`, or a named
  character vector of length 1. See Details.

- pi_level:

  prediction interval level, i.e. the percentiles of the data computed
  within each replicate. Default is `0.90` (90% PI, i.e. the 5th, 50th
  and 95th percentiles).

- ci_level:

  confidence interval level for the ribbons around each percentile
  across replicates. Default is `0.90` (90% CI).

- alpha:

  transparency of the ribbons. Default is `0.15`.

- facet:

  how the stratification variable is displayed when present. `TRUE`
  (default) draws one panel per stratum; `FALSE` overlays the strata in
  a single panel and maps the stratum to the ribbon fill colour.
  Forwarded to
  [`vpcPlot`](https://calvagone.github.io/campsis.doc/reference/vpcPlot.md).

- ...:

  additional arguments (currently unused, reserved for future use)

## Value

a ggplot object

## Details

Stratification is resolved as follows:

- `"auto"` (default): `ARM` is used when more than one distinct arm is
  detected; otherwise `SCENARIO` is used when more than one distinct
  scenario is detected; otherwise `NULL` (no stratification). Only one
  stratification variable is applied because
  [`vpcPlot`](https://calvagone.github.io/campsis.doc/reference/vpcPlot.md)
  supports at most one.

- `NULL`: no stratification.

- named character vector: passed directly to
  [`vpcPlot`](https://calvagone.github.io/campsis.doc/reference/vpcPlot.md)
  (e.g. `c(ARM = "all")` or `c(SCENARIO = "all")`).

## See also

[`vpcPlot`](https://calvagone.github.io/campsis.doc/reference/vpcPlot.md),
[`vpc_plot.pi_campsis_tbl`](https://calvagone.github.io/campsis.doc/reference/vpc_plot.pi_campsis_tbl.md)
