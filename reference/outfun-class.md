# Output function class.

Output function class.

## Slots

- `fun`:

  function or purrr-style lambda formula, first argument 'x' must be the
  results

- `name`:

  name of the output function

- `args`:

  extra arguments, named list

- `packages`:

  packages that must be loaded to execute the given function, character
  vector

- `level`:

  either 'scenario' or 'replicate'. Default is 'scenario'.

- `cls`:

  resulting S3 class(es) of the Campsis output

- `outfun_as_arg`:

  logical, whether to pass the outfun object as an argument to the
  function
