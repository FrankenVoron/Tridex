# Calibration Guide

This guide is a work in progress, and is a collection of different tuning steps that may not be complete or have the supporting configuration parameters. This guide assumes you have followed the previous getting started guide and your printer homes and extrudes filament!

## Rough Offset Calibration

For an IDEX printer, we have 3 offsets that we need to calibrate--X, Y, and Z! Check your IDEX_mode.cfg file and verify that all of your offset variables are set to 0 (variable_offset_x, variable_offset_y, and variable_offset_z). 

First off, it's important that your T0 (left, primary) toolhead is printing well and has a good first layer Z position. Using a hot bed and extruder, move the T0 nozzle to the center of the bed and lower the nozzle until it barely touches a sheet of paper as the paper is moved back and forth. This height should be approximately Z = 0.1mm. Adjust the `[stepper_z]` `position_endstop`, save, restart Klipper, and test until this is true.

Once your T0 nozzle is touching the sheet of paper at 0.1mm, raise the toolhead a few millimeters, switch to T1, and begin lowering the T1 nozzle until it touches the sheet of paper. Record the value--if T1 is touching at 0.17mm and T0 is touching at 0.1mm, the `variable_offset_z` will be T1 - T0 = 0.17 - 0.1 = 0.07mm. Update your IDEX_mode.cfg file and restart Klipper.

Next, let's tune the variable_offset_x! After homing the printer, find an object (such as a block) and place it on the print bed, raise or lower the bed height as necessary so that the nozzle is within a few millimeters of the block. Move the block around until one of the edges is aligned with the center of the T0 nozzle. Record the X position of T0 at this point, then switch to T1, and move the toolhead back and forth in X using the commands in Mainsail until the nozzle is positioned the same as the T0 nozzle was. Record the T1 position, and then calculate the new variable_offset_x as T1_x - T0_x = value. Update your IDEX_mode_cfg file and restart klipper! (Note--if this offset value is very large, you can choose to update the dual_carriage position_endstop instead so that the offset is small)

Finally, tune variable_offset_y. Use the same setup as with X, except adjust the toolheads in Y instead of X! 

These initial calibration values are rough approximate values that will help your printer be in the ballpark. Your Z and Y offsets should be small, generally less than 0.5mm.

## Fine Offset Calibration

It's time for a calibration tuning print! This is a good starter print: [Dual Extruder Calibration Vernier](https://www.thingiverse.com/thing:3873434), Adjust values slightly as needed and reprint until both extruder prints are relatively aligned. 

For a "normal" test print I use [Easter Island Moai - Dual Extrusion Style.](https://www.thingiverse.com/thing:1560492) This is a great print since it allows you to see offsets between the toolheads on the first layer! Adjust offsets as needed, remembering that each offset value is the delta between T0 and T1:

### X Offset Guide

T1 color too far +X (right) => reduce variable_offset_x

T1 color too far -X (left) => increase variable_offset_x

### Y Offset Guide

T1 color too far +Y (back) => reduce variable_offset_y

T1 color too far -Y (front) => increase variable_offset_y

### Z Offset Guide

T1 AND T0 too close to bed => reduce [stepper_z] position_endstop

T1 AND T0 too far from bed => increase [stepper_z] position_endstop

T0 too close to bed, T1 perfect => reduce [stepper_z] position_endstop AND variable_offset_z by same amount

T0 too far from bed, T1 perfect => increase [stepper_z] position_endstop AND variable_offset_z by same amount

T0 perfect, T1 too far from bed => reduce variable_offset_z

T0 perfect, T1 too close to bed => increase variable_offset_z