# Create a time-varying covariate. This covariate will be implemented using EVID=2 rows in the exported dataset and will not use interruption events.

Create a time-varying covariate. This covariate will be implemented
using EVID=2 rows in the exported dataset and will not use interruption
events.

## Usage

``` r
TimeVaryingCovariate(name, table)
```

## Arguments

- name:

  covariate name, character

- table:

  data.frame, must contain the mandatory columns 'TIME' and 'VALUE'. An
  'ID' column may also be specified. In that case, ID's between 1 and
  the max number of subjects in the dataset/arm can be used. All ID's
  must have a VALUE defined for TIME 0.

## Value

a time-varying covariate
