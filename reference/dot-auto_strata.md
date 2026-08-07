# Detect VPC stratification variable automatically.

Returns a named character vector suitable for
[`vpcPlot`](https://calvagone.github.io/campsis.doc/reference/vpcPlot.md)'s
`strata` argument (length 0 or 1), or `NULL` when no stratification is
warranted. `ARM` is preferred over `SCENARIO` when both are
multi-valued.

## Usage

``` r
.auto_strata(x)
```

## Arguments

- x:

  a data frame (typically `std_campsis_tbl`)

## Value

a named character vector or `NULL`
