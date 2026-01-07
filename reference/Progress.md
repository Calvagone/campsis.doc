# Create progress settings.

Create progress settings.

## Usage

``` r
Progress(tick_slice = TRUE)
```

## Arguments

- tick_slice:

  tick() is called after each simulated slice, default is TRUE. In some
  cases, when the number of subjects per slice is low, it may be useful
  disable this flag, to improve performance issues.

## Value

progress settings
