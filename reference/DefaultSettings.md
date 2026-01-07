# Create default settings.

Create default settings.

## Usage

``` r
DefaultSettings(
  engine = "rxode2",
  seed = NULL,
  outvars = character(),
  disabled_variabilities = character(),
  dosing = FALSE
)
```

## Arguments

- engine:

  simulation engine, character

- seed:

  random seed number, integer (or NULL for auto-generated seed)

- outvars:

  output variables, character vector

- disabled_variabilities:

  variabilities to disable in the simulation, character vector

- dosing:

  output dosing information, logical

## Value

default settings
