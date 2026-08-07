# Create default settings.

Create default settings.

## Usage

``` r
DefaultSettings(
  engine = NULL,
  seed = NULL,
  replicates = 1L,
  outvars = character(),
  outfuns = Outfuns(),
  disabled_variabilities = character(),
  dosing = FALSE
)
```

## Arguments

- engine:

  Simulation engine: `'rxode2'` or `'mrgsolve'`. Default is `NULL`
  (unspecified). If `NULL`, `'mrgsolve'` is used first (if installed),
  followed by `'rxode2'` (if installed).

- seed:

  random seed number, integer (or NULL for auto-generated seed)

- replicates:

  number of replicates, integer. Default is 1.

- outvars:

  output variables, character vector

- outfuns:

  output functions, outfuns object

- disabled_variabilities:

  variabilities to disable in the simulation, character vector

- dosing:

  output dosing information, logical

## Value

default settings
