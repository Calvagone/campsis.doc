# Create one or several bolus(es).

Create one or several bolus(es).

## Usage

``` r
Bolus(
  time,
  amount,
  compartment = NULL,
  f = NULL,
  lag = NULL,
  ii = NULL,
  addl = NULL,
  wrap = TRUE,
  ref = NULL,
  rep = NULL
)
```

## Arguments

- time:

  treatment time(s), numeric value or vector. First treatment time if
  used together with ii and addl.

- amount:

  amount to give as bolus, single numeric value

- compartment:

  compartment index or name to give the bolus(es). A vector of integers
  or names can be used for a complex model administration.

- f:

  fraction of dose amount, list of distributions (one per compartment)

- lag:

  dose lag time, list of distributions (one per compartment)

- ii:

  inter-dose interval, requires argument 'time' to be a single numeric
  value

- addl:

  number of additional doses, requires argument 'time' to be a single
  integer value

- wrap:

  if TRUE, the bolus wrapper will be stored as is in the dataset,
  otherwise, it will be split into a list of boluses distinct in time.
  Default is TRUE.

- ref:

  any reference name used to identify this bolus, single character value

- rep:

  repeat the base dosing schedule several times, a 'repeated schedule'
  object is expected. Default is NULL (no repetition).

## Value

a single bolus or a list of boluses
