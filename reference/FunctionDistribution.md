# Create a function distribution. During distribution sampling, the provided function will be responsible for generating values for each sample. If first argument of this function is not the size (n), please tell which argument corresponds to the size 'n' (e.g. list(size="n")).

Create a function distribution. During distribution sampling, the
provided function will be responsible for generating values for each
sample. If first argument of this function is not the size (n), please
tell which argument corresponds to the size 'n' (e.g. list(size="n")).

## Usage

``` r
FunctionDistribution(fun, args)
```

## Arguments

- fun:

  function name, character (e.g. 'rnorm')

- args:

  list of arguments (e.g list(mean=70, sd=10))

## Value

a function distribution
