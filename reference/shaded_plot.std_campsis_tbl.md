# Shaded plot for standard Campsis simulation output.

Plots a median line with a prediction interval ribbon from a
`std_campsis_tbl` (the default output of
[`simulate()`](https://calvagone.github.io/campsis.doc/reference/simulate.md)
when no custom `outfun` is used).

## Usage

``` r
# S3 method for class 'std_campsis_tbl'
shaded_plot(
  x,
  variable = "CONC",
  colour = "auto",
  strat_extra = NULL,
  level = 0.9,
  alpha = 0.25,
  ...
)
```

## Arguments

- x:

  a `std_campsis_tbl` object

- variable:

  name of the column to summarise on the y-axis. Defaults to `"CONC"`.
  An informative error is raised when the column is absent.

- colour:

  stratification for line and ribbon colour. One of `"auto"`, `NULL`, or
  a character vector of column names. See Details.

- strat_extra:

  additional column name(s) used for stratification in the prediction
  interval computation but *not* mapped to colour — useful when combined
  with `facet_wrap()`. Forwarded to
  [`shadedPlot`](https://calvagone.github.io/campsis.doc/reference/shadedPlot.md).
  Default is `NULL`.

- level:

  prediction interval level. Default is `0.90` (90% PI).

- alpha:

  transparency of the ribbon. Default is `0.25`.

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

- character vector: explicit column name(s) to colour/fill by (forwarded
  directly to
  [`shadedPlot`](https://calvagone.github.io/campsis.doc/reference/shadedPlot.md)).

## See also

[`shadedPlot`](https://calvagone.github.io/campsis.doc/reference/shadedPlot.md)
