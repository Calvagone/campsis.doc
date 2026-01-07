# Create hardware settings.

Create hardware settings.

## Usage

``` r
Hardware(
  cpu = 1,
  replicate_parallel = FALSE,
  scenario_parallel = FALSE,
  slice_parallel = FALSE,
  slice_size = NULL,
  dataset_parallel = FALSE,
  dataset_slice_size = 500,
  auto_setup_plan = NULL
)
```

## Arguments

- cpu:

  number of CPU cores to use, default is 1

- replicate_parallel:

  enable parallel computing for replicates, default is FALSE

- scenario_parallel:

  enable parallel computing for scenarios, default is FALSE

- slice_parallel:

  enable parallel computing for slices, default is FALSE

- slice_size:

  number of subjects per simulated slice, default is NULL
  (auto-configured by Campsis depending on the specified engine)

- dataset_parallel:

  enable parallelisation when exporting dataset into a table, default is
  FALSE

- dataset_slice_size:

  dataset slice size when exporting subjects to a table, default is 500.
  Only applicable if 'dataset_parallel' is enabled.

- auto_setup_plan:

  auto-setup plan with the library future, if not set (i.e. =NULL), plan
  will be setup automatically if the number of CPU's \> 1.

## Value

hardware settings
