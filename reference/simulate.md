# Simulate function.

Simulate function.

## Usage

``` r
simulate(
  model,
  dataset,
  dest = NULL,
  events = NULL,
  scenarios = NULL,
  tablefun = NULL,
  outvars = NULL,
  outfun = NULL,
  seed = NULL,
  replicates = 1,
  dosing = FALSE,
  settings = NULL
)

# S4 method for class 'replicated_campsis_model,dataset,character,events,scenarios,function,character,output_function,integer,integer,logical,simulation_settings'
simulate(
  model,
  dataset,
  dest = NULL,
  events = NULL,
  scenarios = NULL,
  tablefun = NULL,
  outvars = NULL,
  outfun = NULL,
  seed = NULL,
  replicates = 1,
  dosing = FALSE,
  settings = NULL
)

# S4 method for class 'campsis_model,dataset,character,events,scenarios,function,character,output_function,integer,integer,logical,simulation_settings'
simulate(
  model,
  dataset,
  dest = NULL,
  events = NULL,
  scenarios = NULL,
  tablefun = NULL,
  outvars = NULL,
  outfun = NULL,
  seed = NULL,
  replicates = 1,
  dosing = FALSE,
  settings = NULL
)

# S4 method for class 'campsis_model,tbl_df,character,events,scenarios,function,character,output_function,integer,integer,logical,simulation_settings'
simulate(
  model,
  dataset,
  dest = NULL,
  events = NULL,
  scenarios = NULL,
  tablefun = NULL,
  outvars = NULL,
  outfun = NULL,
  seed = NULL,
  replicates = 1,
  dosing = FALSE,
  settings = NULL
)

# S4 method for class 'campsis_model,data.frame,character,events,scenarios,function,character,output_function,integer,integer,logical,simulation_settings'
simulate(
  model,
  dataset,
  dest = NULL,
  events = NULL,
  scenarios = NULL,
  tablefun = NULL,
  outvars = NULL,
  outfun = NULL,
  seed = NULL,
  replicates = 1,
  dosing = FALSE,
  settings = NULL
)

# S4 method for class 'campsis_model,tbl_df,rxode_engine,events,scenarios,function,character,output_function,integer,integer,logical,simulation_settings'
simulate(
  model,
  dataset,
  dest = NULL,
  events = NULL,
  scenarios = NULL,
  tablefun = NULL,
  outvars = NULL,
  outfun = NULL,
  seed = NULL,
  replicates = 1,
  dosing = FALSE,
  settings = NULL
)

# S4 method for class 'campsis_model,tbl_df,mrgsolve_engine,events,scenarios,function,character,output_function,integer,integer,logical,simulation_settings'
simulate(
  model,
  dataset,
  dest = NULL,
  events = NULL,
  scenarios = NULL,
  tablefun = NULL,
  outvars = NULL,
  outfun = NULL,
  seed = NULL,
  replicates = 1,
  dosing = FALSE,
  settings = NULL
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

dataframe with all results
