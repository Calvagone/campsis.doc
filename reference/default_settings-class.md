# Default settings class.

Default settings class.

## Slots

- `engine`:

  Simulation engine: `'rxode2'` or `'mrgsolve'`. Default is `NULL`
  (unspecified). If `NULL`, `'mrgsolve'` is used first (if installed),
  followed by `'rxode2'` (if installed).

- `seed`:

  random seed number, integer

- `replicates`:

  number of replicates, integer

- `outvars`:

  output variables, character vector

- `outfuns`:

  output functions, outfuns object

- `disabled_variabilities`:

  variabilities to disable in the simulation, character vector

- `dosing`:

  output dosing information, logical
