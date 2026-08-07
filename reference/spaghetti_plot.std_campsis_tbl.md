# Spaghetti plot for standard Campsis simulation output.

Plots individual-level time profiles from a `std_campsis_tbl` (the
default output of
[`simulate()`](https://calvagone.github.io/campsis.doc/reference/simulate.md)
when no custom `outfun` is used).

## Usage

``` r
# S3 method for class 'std_campsis_tbl'
spaghetti_plot(x, variable = "CONC", colour = "auto", ...)
```

## Arguments

- x:

  a `std_campsis_tbl` object

- variable:

  name of the column to plot on the y-axis. Defaults to `"CONC"`. An
  informative error is raised when the column is absent.

- colour:

  stratification for line colour. One of `"auto"`, `NULL`, or a
  character vector of column names. See Details.

- ...:

  additional arguments (currently unused, reserved for future use)

## Value

a ggplot object

## Details

Colour stratification is resolved as follows:

- `"auto"` (default): `ARM` is added when more than one distinct arm is
  detected in the data; `SCENARIO` is added when more than one distinct
  scenario is detected.

- `NULL`: no colour mapping.

- character vector: explicit column name(s) to colour by (forwarded
  directly to
  [`spaghettiPlot`](https://calvagone.github.io/campsis.doc/reference/spaghettiPlot.md)).

## See also

[`spaghettiPlot`](https://calvagone.github.io/campsis.doc/reference/spaghettiPlot.md)
