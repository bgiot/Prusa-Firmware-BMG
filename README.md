# Prusa-Firmware-BMG

This repository contains my personal build of the Prusa MK3 printer firmware with specific settings for Bondtech Extruder

**Thanks to Chris Warkocki for his work on these settings!**

__Use those custom firmwares at your own risk.__

> **_As flashing the firmware doesn't update eeprom settings, you still need to apply e-step change command!_**

## MK3/MK3S

### The commands to update the eeprom are:

```
M350 E16 ; 16 for 1.8°, 8 for 0.9°
M92 E415 ; Make sure to run this command after the previous one!
M500 ; save settings
```


### The changes in the firmware are:

``` C
#define DEFAULT_AXIS_STEPS_PER_UNIT   {100,100,3200/8,415}
#define TMC2130_UNLOAD_CURRENT_R 12
#define LOAD_FILAMENT_2 "G1 E50 F100"
#define UNLOAD_FILAMENT_1 "G1 E-100 F7000"
#define FILAMENTCHANGE_FINALFEED 35
#define TMC2130_USTEPS_E    16 // 8 for 0.9° stepper
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


## You want to compile yourself ?

I forked the official Prusa repository and use a specific branch with all my custom changes.  
You can have a look at my changes at: https://github.com/bgiot/Prusa-Firmware/tree/BMGCustom  

Each time a new version is released in the official repository, I'll merge it in my custom branch.

You can easily compile from my custom branch.   
You just need Microsoft __Visual Studio Code__ and the extension __PlatformIO IDE__.

~~**_Note: Building 3.8.0 with platform.io gives issues.  Use Arduino IDE for the moment.  I'm working on a fix._**
~~

