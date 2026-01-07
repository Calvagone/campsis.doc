# Create an interruption event.

Create an interruption event.

## Usage

``` r
Event(name = NULL, times, fun, debug = FALSE)
```

## Arguments

- name:

  event name, character value

- times:

  interruption times, numeric vector

- fun:

  event function to apply at each interruption

- debug:

  output the variables that were changed through this event

## Value

an event definition
