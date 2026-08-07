# Restore a campsis_tbl object

Internal vctrs method to restore the custom \`campsis_tbl\` class
attributes, specifically copying over the S4 metadata object, after a
vector operation.

## Usage

``` r
# S3 method for class 'campsis_tbl'
vec_restore(x, to, ...)
```

## Arguments

- x:

  A tibble or vector to restore.

- to:

  The original \`campsis_tbl\` object to restore to.

- ...:

  Additional arguments passed to methods.

## Value

A restored \`campsis_tbl\` object with appropriate metadata and classes.
