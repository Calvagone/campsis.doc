# Get all distinct times for the specified object.

Get all distinct times for the specified object.

## Usage

``` r
get_times(object, ...)

# S4 method for class 'treatment'
get_times(object, unwrap = TRUE)

# S4 method for class 'observations'
get_times(object, doseTimes = NULL)

# S4 method for class 'observations_set'
get_times(object, doseTimes = NULL)

# S4 method for class 'arm'
get_times(object)

# S4 method for class 'arms'
get_times(object)

# S4 method for class 'events'
get_times(object)

# S4 method for class 'dataset'
get_times(object)
```

## Arguments

- object:

  any object

- ...:

  extra arguments like \`doseTimes\` in observations or \`unwrap\` in
  treatment

- unwrap:

  unwrap treatment before accessing the times, default value is TRUE

- doseTimes:

  times of the doses, only needed if a \[DosingSchedule()\] is referred
  to

## Value

numeric vector with all unique times, sorted
