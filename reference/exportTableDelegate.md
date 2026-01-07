# Export table delegate.

Export table delegate.

## Usage

``` r
exportTableDelegate(model, dataset, dest, events, seed, tablefun, settings)
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

- seed:

  seed value

- tablefun:

  function or lambda formula to apply on exported 2-dimensional dataset

- settings:

  advanced simulation settings

## Value

a data frame
