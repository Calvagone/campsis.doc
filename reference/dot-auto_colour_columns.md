# Detect colour stratification columns automatically.

Adds `"ARM"` when the column exists and contains more than one distinct
value. Same logic for `"SCENARIO"`.

## Usage

``` r
.auto_colour_columns(x)
```

## Arguments

- x:

  a data frame (typically `std_campsis_tbl`)

## Value

a character vector of column names to colour by, or `NULL`
