# Does the data contain more than one replicate?

Does the data contain more than one replicate?

## Usage

``` r
.is_replicated(x)
```

## Arguments

- x:

  a data frame (typically `std_campsis_tbl`)

## Value

`TRUE` if the data contains a `replicate` column with more than one
distinct value, `FALSE` otherwise
