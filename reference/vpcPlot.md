# VPC plot.

VPC plot.

## Usage

``` r
vpcPlot(x, scenarios = NULL, level = 0.9, alpha = 0.15)
```

## Arguments

- x:

  data frame, output of CAMPSIS with replicates

- scenarios:

  scenarios, character vector, NULL is default

- level:

  PI level, default is 0.9 (90% PI)

- alpha:

  alpha parameter (transparency) given to geom_ribbon

## Value

a ggplot object
