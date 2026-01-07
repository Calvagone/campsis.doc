# Create a treatment arm.

Create a treatment arm.

## Usage

``` r
Arm(id = as.integer(NA), subjects = 1, label = as.character(NA))
```

## Arguments

- id:

  unique identifier for this arm (available trough dataset), integer. If
  NA (default), this identifier is auto-incremented.

- subjects:

  number of subjects in arm, integer

- label:

  arm label, single character string. If set, this label will be output
  in the ARM column of CAMPSIS instead of the identifier.

## Value

an arm
