# Simulation delegate (several replicates).

Simulation delegate (several replicates).

## Usage

``` r
simulateDelegate(
  model,
  dataset,
  dest,
  events,
  scenarios,
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

- scenarios:

  list of scenarios to be simulated

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
