# Prusa-Firmware-BMG

This repository contains my personal build of the Prusa MK3 printer firmware with specific settings for Bondtech Extruder

**Thanks to Chris Warkocki for his work on these settings!**


> **_As flashing the firmware doesn't update eeprom settings, you still need to apply e-step change command!_**

## MK3/MK3S

### The commands to update the eeprom are:

```
M92 E830
M500
```


### The changes in the firmware are:

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


## MK2.5 (RAMBo1.3)

For 1.8° motor:

```
M92 E415
M500
```

For 0.9° motor:

```
M92 E830
M500
```

### The changes in the firmware are:

``` C
#define DEFAULT_AXIS_STEPS_PER_UNIT   {100,100,3200/8,415}  // 830 for the BMG-16
#define LOAD_FILAMENT_2 "G1 E50 F100"
#define UNLOAD_FILAMENT_1 "G1 E-100 F4800" // F2400 for the BMG-16
#define FILAMENTCHANGE_FINALFEED 35
```
