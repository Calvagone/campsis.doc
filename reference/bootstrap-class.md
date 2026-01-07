# Bootstrap class.

Bootstrap class.

## Slots

- `data`:

  data frame to be bootstrapped. Column 'BS_ID' is mandatory and
  corresponds to the original row ID from the bootstrap. It must be
  numeric and unique. Other columns are covariates to be bootstrapped
  (row by row).

- `replacement`:

  values can be reused or not, logical

- `random`:

  values are drawn randomly, logical

- `export_id`:

  tell CAMPSIS if 'BS_ID' must be exported into the dataset, logical
