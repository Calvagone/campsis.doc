# VPC plot.

VPC plot.

## Usage

``` r
vpcPlot(x, strata = NULL, level = 0.9, alpha = 0.15, facet = TRUE)
```

## Arguments

- x:

  data frame, output of Campsis with replicates

- strata:

  named vector with the strata to use, default is c(SCENARIO="all",
  ARM="all"). Only columns that are actually present in `x` are used.

- level:

  PI level, default is 0.9 (90% PI)

- alpha:

  alpha parameter (transparency) given to geom_ribbon

- facet:

  how the stratification variable is displayed. `TRUE` (default) draws
  one panel per stratum with `facet_wrap()`, keeping the median band red
  and the outer bands blue. `FALSE` overlays the strata in a single
  panel, mapping the stratum to the ribbon fill colour (the median band
  is drawn more opaque than the outer bands). Ignored when no
  stratification is requested.

## Value

a ggplot object
