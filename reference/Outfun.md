# Create a new output function

Create a new output function

## Usage

``` r
Outfun(
  fun = function(x, ...) {
     x
 },
  args = list(),
  packages = NULL,
  level = "replicate",
  name = "custom"
)
```

## Arguments

- fun:

  function or purrr-style lambda formula, first argument 'x' must be the
  results

- args:

  extra arguments, named list

- packages:

  packages that must be loaded to execute the given function, character
  vector

- level:

  where to apply the output function, only 'replicate' is allowed since
  Campsis v1.9.0

- name:

  name of the output function. Default is 'custom'.

## Value

an output function
