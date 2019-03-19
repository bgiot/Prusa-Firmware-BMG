# Prusa-Firmware-BMG

This repository contains my personal build of the Prusa MK3 printer firmware with specific settings for Bondtech Extruder

__Thanks to Chris Warkocki for his work on this settings!__

The changes are:

``` C
#define DEFAULT_AXIS_STEPS_PER_UNIT   {100,100,3200/8,830}
#define TMC2130_UNLOAD_CURRENT_R 20
#define LOAD_FILAMENT_2 "G1 E50 F100"
#define UNLOAD_FILAMENT_1 "G1 E-100 F7000"
#define FILAMENTCHANGE_FINALFEED 35
```


Also, for the 1/16 (0.9° stepper), there is an extra change:

``` C
#define TMC2130_USTEPS_E    16
```
