# Apply output function(s) on the given Campsis results.

Apply output function(s) on the given Campsis results.

## Usage

``` r
apply_outfun(x, outfun, level = NULL, ...)

# S4 method for class 'outfun'
apply_outfun(x, outfun, level = NULL, ...)

# S4 method for class 'outfuns'
apply_outfun(x, outfun, level = NULL, ...)
```

## Arguments

- x:

  Campsis simulation results

- outfun:

  output function(s), an \`outfun\` or \`outfuns\` object

- level:

  level at which the output function is applied, 'replicate' by default

- ...:

  extra arguments transmitted automatically by Campsis (e.g.
  \`replicate\` for the replicate number)

## Value

the updated Campsis results
