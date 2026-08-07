# Create a prediction interval output function

Create a prediction interval output function

## Usage

``` r
PIOutfun(
  variable,
  strata = get_default_strata(),
  level = 0.9,
  name = sprintf("pi_%s_%i%%", paste0(variable, collapse = "_"), round(level * 100))
)
```

## Arguments

- variable:

  variable(s) used to compute the prediction interval, character vector

- strata:

  named vector with the strata to use, default is c(SCENARIO="all",
  ARM="all")

- level:

  PI level, default is 0.9 (90% PI)

- name:

  name of the output function. Default is
  'pi\_\<variable\>\_\<level\>pc'.

## Value

a pi_outfun object
