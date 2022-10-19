# Initial Startup Guide

This guide is heavily inspired by Klipper's Configuration Check guide: https://www.klipper3d.org/Config_checks.html

## 1. Klipper Setup

Flash MainsailOS or FluiddPi to your Raspberry Pi micro SD card, and configure your microcontroller and CAN interfaces. There are a variety of different resources available that may be helpful, but it is expected that you will be comfortable flashing/configuring the device that you choose!

- [MainsailOS](https://github.com/mainsail-crew/MainsailOS/tags)
- [FluiddPi](https://github.com/fluidd-core/FluiddPI/tags)
- [Klipper Mainsail CAN Setup Guide](https://www.youtube.com/watch?v=XkcxSQhRR3I)
- [CanBoot Flashing Guide](https://youtu.be/YrF99Sff9g8)
- [BTT EBB V1.0 CAN Setup Guide](https://youtu.be/_FELCN8CbWA)

## 2. Configuration

### Endstop Checks

Save the firmware configuration files from the Tridex Github to your printer, and edit them to match your control boards and printer specification. Once Klipper starts successfully without throwing errors, verify each of the endstops to make sure they function as expected by manually triggering the endstop with your finger or a tool. The status can be checked in the "Machine" page of Mainsail by refreshing the endstop status section.

- Endstop X (left toolhead X endstop)
- Endstop Dual_Carriage (right toolhead X endstop)
- Endstop Y (left Y endstop)
- Endstop Y1 (right Y endstop)
- Endstop Z (Z nozzle pin)
- Probe (Omron probe or Klicky, etc)

Once each endstop is configured so that it reads `Triggered` when pressed, and `Open` when not pressed, go ahead and push the X axis towards the back of the printer and make sure that both Y endstops trigger off of the X axis. If only one can trigger, tighten or loosen one of the X belt tensioners until both trigger approximately simultaneously. Also, verify that the T0 (left) toolhead X endstop can physically trigger off of the left XY joint, and that the T1 (right) toolhead X endstop can trigger off of the T0 (left) toolhead. 

### Stepper Motors

Next, let's talk about stepper motors checks! Similar to single toolhead Voron printers, the origin (X=0, Y=0) is located at the front left corner of the bed, with positive X traveling to the right, and positive Y movement traveling to the back. For starters, we need to make sure all of the motors are connected to the right connectors and are moving the correct directions. For this, we will use  `STEPPER_BUZZ STEPPER=[stepper name]`. This command will move the stepper back and forth--the first movement after sending the command will be in the "+" axis direction, and then "-". 

- `STEPPER_BUZZ STEPPER=stepper_x` - T0 (left toolhead) should move right (+), then left (-)
- `STEPPER_BUZZ STEPPER=dual_carriage` - T1 (right toolhead) should move right (+) then left (-)
- `STEPPER_BUZZ STEPPER=stepper_y` - left Y motor should move back (+) and then to the front (-)
- `STEPPER_BUZZ STEPPER=stepper_y1` - right Y motor should move back (+) and then front (-)
- `STEPPER_BUZZ STEPPER=stepper_z`- front left Z motor should move down (+) and then up (-)
- `STEPPER_BUZZ STEPPER=stepper_z1`- back Z motor should move down (+) and then up (-)
- `STEPPER_BUZZ STEPPER=stepper_z2`- front right Z motor should move down (+) and then up (-)

### Homing

Next, we need to check the homing sequence. The order of homing is different with a Tridex than with a Trident. An overview of the order is as follows:

1. Home Y to Y=max (back of printer)
2. Home T0 (left toolhead) to X=min (left of printer)
3. Home T1 (right toolhead) to T0 (left of printer)
4. Move T1/Park T1
5. Move T0 to Z endstop pin location
6. Home Z

The default printer configuration file already has homing set up properly for you, however, this configuration file may be updated in the future to be more universal and user friendly. For now, follow these steps **and be sure to have access to the "Emergency Stop" button in Mainsail/Fluidd**:

1. Use macro `IDEX_HOME_Y` (visible on Mainsail dashboard). The printer should move the X axis backwards until both Y endstops are triggered, and then move forward approximately 35mm. **If it moves to the front of the printer at first and doesn't stop, hit the Emergency Stop button! If the Y motors move in opposite directions, hit the Emergency Stop button!** 

If either of these cases occurs--double check your STEPPER_BUZZ commands and invert the direction pin of the stepper motor that is not traveling in the correct direction. Also, double check your `position_endstop`--it should be set equal to position_max. If it is set to something else (like position_min)--the printer will home in the incorrec direction. 

2. Once you have successfully homed Y, use macro `IDEX_HOME_X`. The printer should move the left toolhead (T0, controlled by stepper_x) to the left until it triggers the T0 x endstop, and then it should move the right toolhead (T1, controlled by dual_carriage) to the left until it triggers the T1 x endstop. Then, it should move the T1 toolhead to the right to about the middle of the printer, and then move it to the parked position close to the right of the X axis. T0 should become active at this point, and move to about the center of the printer. **If either toolhead doesn't travel in the correct direction, or crashes, press the Emergency Stop Button immediately!** 

The initial printer.cfg in the Tridex repository should properly define the `position_endstop` for both `stepper_x` and `dual_carriage`, but if you have issues with homing, double check both the `STEPPER_BUZZ` directions and toolheads as well as the position endstop for both. `[stepper_x]` should have a `position_min` and `position_endstop` of approximately -50, and `[dual_carriage]`should have `position_min` and `position_endstop` of approximately 22. 

3. Once both X and Y have homed successfully, (by running `IDEX_HOME_Y` and then `IDEX_HOME_X`), make sure T0 is active (press the T0 button in Mainsail), and move the toolhead using Mainsail until the nozzle is above the Z endstop pin. Record these coordinates (X and Y) and update your [homing_override] section so that the toolhead goes to this point prior to homing Z. (More documentation needs to be added for this step). Your z pin location should be somewhere close to X = 145-150mm and Y = 250-255mm for a standard 250x250mm Tridex build. 
4. Once you have updated your configuration, saved it, and restarted klipper, now is the exciting point! Press the "Home All" button in Mainsail. The printer should home Y, home X, and then move T0 to the Z endstop pin location and home. **Be sure to be ready to press the Emergency Stop button!** 

Even if the nozzle touches the Z endstop pin successfully, double check the location again and make sure that the nozzle is as close to the center of the Z endstop pin as possible. With this final adjustment, save the configuration, restart the printer, and home again!

5. Finally, we need to verify that the probe works as expected! If you are using an inductive probe, make sure that the probe triggers off of a piece of metal and the bed by checking the endstop status. Then, run a Z_TILT_ADJUST (or "Z-TILT" in Mainsail) to level the bed. Finish by running a final G28 to home Z again off of the Z pin. 

Congratulations! You've successfully homed your Tridex printer!

### Heaters and Fans

Follow the standard [Klipper Configuration Checks](https://www.klipper3d.org/Config_checks.html) guide to test each of your hotend fans, hotend heaters, part cooling fans, and bed heater. PID calibrate each heater individually, saving the configuration after each tune.

### Extruder

With your hotend heated, try extruding some filament through each toolhead. If the extruder is going in the wrong direction (retracting instead of feeding filament), invert the direction pin for that given extruder. Press the "T0" or "T1" buttons to switch between toolheads to test each one. Finally, calibrate your extruder by extruding 100mm of filament and verifying that 100mm of filament is fed through the extruder. It is critical that both extruders are functionally extruding the same amount of filament!