---
title: Notable Support Figure
tags: [Notebooks/Engineering/General]
created: 2022-01-27T15:46:54.198Z
modified: 2022-01-27T19:26:28.609Z
---

# Notable Support Figure

```pikchr
$percent_start = 0.29
$percent_current = 0.35
$donation1_current = 35
$donation1_max = 100

$color_thermometer = 0xe0e0e0
$color_baseline = 0xE0ABE0
$color_current = 0xff00ff
$color_donation = 0x80ff80

$width = 4.0
$height = 0.2
$margin = 0.04
$bubble_margin = 0.5

circlerad = 0.22

// ---------------
// Funding
// ---------------

// Thermometer bar
Thermometer: box width $width height $height fill $color_thermometer
text "CURRENT SUPPORT LEVEL" bold with .s at Thermometer.n
$current_width = $width * $percent_current
Current: box width $current_width height $height fill $color_current with .w at Thermometer.w
$baseline_width = $width * $percent_start
Baseline: box width $baseline_width height $height fill $color_baseline with .w at Thermometer.w
// Endpoint text
text "$0" with .e at $margin left of Thermometer.w
text "$580" with .w at $margin right of Thermometer.e
// Bubbles
circle "$165" "(29%)" with .c at $bubble_margin heading 180+45 from Baseline.se fill $color_baseline
arrow from previous.ne to Baseline.se
circle "$200" "(35%)" with .c at $bubble_margin heading 180-45 from Current.se fill $color_current
arrow from previous.nw to Current.se

// ---------------
// Donation #1
// ---------------
T2: box width $width height $height fill $color_thermometer at 1.1 south of Thermometer
text "DONATION #1 (Match the support increase, up to $100)" bold with .s at T2.n
text "$0" with .e at $margin left of T2.w
text "$100" with .w at $margin right of T2.e
$donation1_width = $width * $donation1_current / $donation1_max
Donation1: box width $donation1_width height $height fill $color_donation with .w at T2.w
text "$35" with .n at $margin/2  south of Donation1.se 

// ---------------
// Donation #2
// ---------------
T3: box width $width height $height fill $color_thermometer at 0.7 south of T2
text "DONATION #2 (Hit the support goal of $580)" bold with .s at T3.n
text "$0" with .e at $margin left of T3.w
text "$100" with .w at $margin right of T3.e
```

