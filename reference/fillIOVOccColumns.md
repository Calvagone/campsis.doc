# Fill IOV/Occasion columns.

Problem in RxODE (LOCF mode) / mrgsolve (LOCF mode), if 2 rows have the
same time (often: OBS then DOSE), first row covariate value is taken!
Workaround: identify these rows (group by ID and TIME) and apply a fill
in the UP direction.

## Usage

``` r
fillIOVOccColumns(table, columnNames, downDirectionFirst)
```

## Arguments

- table:

  current table

- columnNames:

  the column names to fill

- downDirectionFirst:

  TRUE: first fill down then fill up (by ID & TIME). FALSE: First fill
  up (by ID & TIME), then fill down

## Value

2-dimensional dataset
