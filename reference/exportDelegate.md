# Export delegate method. This method is common to RxODE and mrgsolve.

Export delegate method. This method is common to RxODE and mrgsolve.

## Usage

``` r
exportDelegate(object, dest, model, arm_offset = NULL, offset_within_arm = 0)
```

## Arguments

- object:

  current dataset

- dest:

  destination engine

- model:

  Campsis model, if provided, ETA's will be added to the dataset

- arm_offset:

  arm offset (on ID's) to apply when parallelisation is used. Default
  value is NULL, meaning parallelisation is disabled. Otherwise, it
  corresponds to the offset to apply for the current arm being exported
  (in parallel).

- offset_within_arm:

  offset (on ID's) to apply within the current arm being exported (only
  used when parallelisation is enabled), default is 0

## Value

2-dimensional dataset, same for RxODE and mrgsolve
