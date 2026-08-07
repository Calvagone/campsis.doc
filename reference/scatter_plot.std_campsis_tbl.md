# Scatter plot for standard Campsis simulation output.

Plots one or two variables against each other at a given time point,
from a `std_campsis_tbl` (the default output of
[`simulate()`](https://calvagone.github.io/campsis.doc/reference/simulate.md)
when no custom `outfun` is used).

## Usage

``` r
# S3 method for class 'std_campsis_tbl'
scatter_plot(x, variable = "CONC", colour = "auto", time = NULL, ...)
```

## Arguments

- x:

  a `std_campsis_tbl` object

- variable:

  character vector of length 1 or 2 giving the column name(s) to plot.
  Defaults to `"CONC"`. An informative error is raised when any column
  is absent.

- colour:

  stratification for point colour. One of `"auto"`, `NULL`, or a
  character vector of column names. See Details.

- time:

  numeric vector of time point(s) to filter to before plotting. When
  `NULL` (default) the minimum time in the data is used (typically time
  0), which is useful for plotting individual parameters. Forwarded to
  [`scatterPlot`](https://calvagone.github.io/campsis.doc/reference/scatterPlot.md).

- ...:

  additional arguments (currently unused, reserved for future use)

## Value

a ggplot object

## Details

When a single variable is supplied it is plotted on the x-axis with y
fixed to 0, producing a 1-D strip chart. When two variables are supplied
the first is mapped to x and the second to y.

Colour stratification is resolved as follows:

- `"auto"` (default): `ARM` is added when more than one distinct arm is
  detected in the data; `SCENARIO` is added when more than one distinct
  scenario is detected.

- `NULL`: no colour mapping.

- character vector: explicit column name(s) to colour by (forwarded
  directly to
  [`scatterPlot`](https://calvagone.github.io/campsis.doc/reference/scatterPlot.md)).

## See also

[`scatterPlot`](https://calvagone.github.io/campsis.doc/reference/scatterPlot.md)
