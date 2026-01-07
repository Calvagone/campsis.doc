# Solver settings class. See ?mrgsolve::update. See ?rxode2::rxSolve.

Solver settings class. See ?mrgsolve::update. See ?rxode2::rxSolve.

## Slots

- `atol`:

  absolute solver tolerance, default is 1e-08

- `rtol`:

  relative solver tolerance, default is 1e-08

- `hmax`:

  limit how big a solver step can be, default is NA

- `maxsteps`:

  max steps between 2 integration times (e.g. when observations records
  are far apart), default is 70000

- `method`:

  solver method, for RxODE/rxode2 only: 'liblsoda' (default), 'lsoda',
  'dop853', 'indLin'. Mrgsolve's method is always 'lsoda'.
