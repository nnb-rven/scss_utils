# SCSS Function: `rounder`

A custom SCSS function to round a numeric value to a specified number of decimal places. This is especially useful when you need precise rounding in stylesheets for values like percentages, rem units, or other computed values.

## Function Definition

```scss
@use 'sass:math';

@function rounder($value, $decimal_places: 3) {
  $e: math.pow(10, $decimal_places);

  @return math.div(math.round($value * $e), $e);
}
