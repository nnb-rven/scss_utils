# SCSS Function: `scale`

A custom SCSS function to scale a value based on a weight and within a specified range. This can be useful for creating dynamic scaling behaviors in your stylesheets.

## Function Definition

```scss
@use 'sass:math';

@function scale($value, $weight, $range_min, $range_max, $precise: 100) {
  $interval: if(($weight > 0), ($range_max - $value), ($value - $range_min));
  $scale: math.div(($weight * $interval), $precise);
  $value: ($value + $scale);

  @return $value;
}
