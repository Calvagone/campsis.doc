# Simulation delegate core (single replicate).

Simulation delegate core (single replicate).

## Usage

``` r
simulateDelegateCore(
  model,
  dataset,
  dest,
  events,
  tablefun,
  outvars,
  outfun,
  seed,
  replicates,
  dosing,
  settings
)
```

## Arguments

- model:

  generic CAMPSIS model

- dataset:

  CAMPSIS dataset or 2-dimensional table

- dest:

  destination simulation engine, default is 'RxODE'

- events:

  interruption events

- tablefun:

  function or lambda formula to apply on exported 2-dimensional dataset

- outvars:

  variables to output in resulting dataframe

- outfun:

  an output function to apply on the simulation results. Type ?Outfun
  for more info.

- seed:

  seed value

- replicates:

  number of replicates, default is 1

- dosing:

  output dosing information, default is FALSE

- settings:

  advanced simulation settings

## Value

a data frame with the results
