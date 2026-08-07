# Create a NCA table output function

Create a NCA table output function

## Usage

``` r
NCATableOutfun(table, export_type = "summary", name = "default_nca_table")
```

## Arguments

- table:

  NCA table from campsisnca, object, path to JSON, or JSON element

- export_type:

  type of export, 'summary', 'summary_wide', 'summary_pretty',
  'individual' or 'individual_wide'

- name:

  name of the output function. Default is 'default_nca_table'.

## Value

a stats_outfun object
