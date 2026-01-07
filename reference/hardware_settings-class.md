# Hardware settings class.

Hardware settings class.

## Slots

- `cpu`:

  number of CPU cores to use, default is 1

- `replicate_parallel`:

  enable parallel computing for replicates, default is FALSE

- `scenario_parallel`:

  enable parallel computing for scenarios, default is FALSE

- `slice_parallel`:

  enable parallel computing for slices, default is FALSE

- `slice_size`:

  number of subjects per simulated slice, default is NULL
  (auto-configured by Campsis depending on the specified engine)

- `dataset_parallel`:

  enable parallelisation when exporting dataset into a table, default is
  FALSE

- `dataset_slice_size`:

  dataset slice size when exporting subjects to a table, default is 500.
  Only applicable if 'dataset_parallel' is enabled.

- `auto_setup_plan`:

  auto-setup plan with the library future, default is FALSE
