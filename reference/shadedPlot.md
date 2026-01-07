# Shaded plot (or prediction interval plot).

Shaded plot (or prediction interval plot).

## Usage

``` r
shadedPlot(
  x,
  output,
  colour = NULL,
  strat_extra = NULL,
  level = 0.9,
  alpha = 0.25
)
```

## Arguments

- x:

  data frame

- output:

  variable to show

- colour:

  variable(s) to colour

- strat_extra:

  variable(s) to stratify, but not to colour (useful for use with
  facet_wrap)

- level:

  PI level, default is 0.9 (90% PI)

- alpha:

  alpha parameter (transparency) given to geom_ribbon

## Value

a ggplot object
