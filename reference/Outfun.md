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
  level = "scenario"
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

  either 'scenario' or 'replicate'. Default is 'scenario'.

## Value

an output function
