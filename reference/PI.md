# Compute the prediction interval summary over time.

Compute the prediction interval summary over time.

## Usage

``` r
PI(x, output, scenarios = NULL, level = 0.9, gather = TRUE)
```

## Arguments

- x:

  data frame

- output:

  variable to show, character value

- scenarios:

  scenarios, character vector, NULL is default

- level:

  PI level, default is 0.9 (90% PI)

- gather:

  FALSE: med, low & up columns, TRUE: metric column

## Value

a summary table
