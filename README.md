This is my fork of the Prusa Firmware for the MK3.
I have built a Prusa MK3 clone with a Titan Aqua clone from Aliexpress.
You can follow the details at http://theprusamk3clone.blogspot.com

In order to work with my printer I had to change some configuration parameters in the Configuration_Prusa.h to fit.

These are the changes that I made.

As the Titan Aqua is a geared extruder I needed to adjust the steps per mm and the direction:

#define DEFAULT_AXIS_STEPS_PER_UNIT {100,100,3200/8,840}
#define INVERT_E0_DIR 1 // for direct drive extruder v9 set to 1, for geared extruder set to 0

As my nozzle is slightly higher that the standard MK3 E3D V6 hot end my z height is bigger. If it is not adjusted, the calibration will fail.

#define Z_MAX_POS 218

The PINDA Probe is also at a different distance to the nozzle, so we have to adjust this.

#define X_PROBE_OFFSET_FROM_EXTRUDER 30 // Z probe to nozzle X offset: -left +right
#define Y_PROBE_OFFSET_FROM_EXTRUDER 45 // Z probe to nozzle Y offset: -front +behind

That is basically all I needed to change to get my printer working.
