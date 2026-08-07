# Assert that one or more variable columns are present in the data.

Raises an informative error listing all absent column names.

## Usage

``` r
.assert_variable_present(x, variable)
```

## Arguments

- x:

  a data frame

- variable:

  character vector of column name(s) to check

## Value

invisibly `NULL`; called for its side-effect
