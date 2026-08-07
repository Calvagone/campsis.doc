# VPC plot for prediction-interval Campsis output.

Plots VPC ribbons (a confidence interval around the median, lower and
upper percentiles) from a `pi_campsis_tbl`, i.e. the output of
[`simulate()`](https://calvagone.github.io/campsis.doc/reference/simulate.md)
with multiple replicates and a
[`PIOutfun`](https://calvagone.github.io/campsis.doc/reference/PIOutfun.md).
Such data already contains the per-replicate prediction interval in long
format (columns `replicate`, `TIME`, `metric` with values `"low"` /
`"med"` / `"up"` and `value`). This method only needs to compute the
confidence interval around each percentile across replicates.

## Usage

``` r
# S3 method for class 'pi_campsis_tbl'
vpc_plot(x, strata = "auto", level = 0.9, alpha = 0.15, facet = TRUE, ...)
```

## Arguments

- x:

  a `pi_campsis_tbl` object with a `replicate` column

- strata:

  stratification for the VPC. One of `"auto"`, `NULL`, or a named
  character vector of length 1. See Details.

- level:

  confidence interval level for the ribbons around each percentile.
  Default is `0.90` (90% CI).

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
[`PIOutfun`](https://calvagone.github.io/campsis.doc/reference/PIOutfun.md)
