# Assembly Guide for Tridex Gantry

This guide is meant to be a supplement to the standard Voron Trident and Voron Stealthburner/CW2 assembly manuals. It is not official, or final, but hopefully it will help you figure out the order of operations and make life a little bit simpler!

## Part 1: Basic Assembly

Follow the Trident manual, skipping the Front Idler, A/B Drive, and X Axis assembly. You may mount the entire Z assembly including the deck panel, bed, and electronics, and remake the CW2 and Stealthburner fan assemblies per the Stealthburner manual. Mount the Y MGN9 rails to the Y extrusions, but leave the screws loose so that they can slide slightly back and forth.

## Part 2: Drive Modules

Follow PDF instructions in this folder for drive module assembly. Once they are completed, install each drive module onto the gantry extrusions with M5x16 BHCS and M5x10 BHCS.

![Fusion360_jOAN20uSyg](https://user-images.githubusercontent.com/11861478/198882337-b68666b8-15e0-41cd-8b73-8d8e9634e809.png)

## Part 3: Front Idlers

Follow PDF instructions in this folder for front idler assembly. Once they are completed, install each front idler onto the gantry extrusions using M5x16 BHCS and M5x10 BHCS.

![Fusion360_WQIAOHZXhy](https://user-images.githubusercontent.com/11861478/198882399-be3b83a5-03ee-4053-9f05-458af4c4baae.png)

After securing the front idlers and drive modules, install/slide the MGN9 Y rails backwards until they contact the drive modules. Use the MGN9 3d printed alignment tools to make sure the rail is centered, and secure the rail to the 2020 extrusion.

![Fusion360_HXndMWOubw](https://user-images.githubusercontent.com/11861478/198882496-b5818bec-bf86-4203-ba7d-38b0c528f782.png)

There will be a gap on the front idlers. This is to allow variation in MGN9 length as well as make it easier to install/remove the drive modules/front idlers if needed in the future without completely removing the MGN9 rail. 

![Fusion360_wkdUuxeDLE](https://user-images.githubusercontent.com/11861478/198882592-ce803de0-4dc9-4b81-946b-10bda13a6309.png)

## Part 4: XY Joints/Y Belts

Unlike standard Voron Trident XY joint assemblies, the Tridex XY joints must be assembled on the printer in stages. Mount the XY joint lowers to the MGN9 Y rails:

![Fusion360_Avvm7I7o4f](https://user-images.githubusercontent.com/11861478/198882642-7c12b489-7e8f-42ce-8aa5-1d60840bf631.png)

Then, take a length of GT2 belt and feed it through the back of the front idler, loop around a GT2 idler, and then feed it through the other opening in the front idler:

![Fusion360_W7kKqY3unr](https://user-images.githubusercontent.com/11861478/198882913-fbe16b50-f011-455f-a9c3-72717587b1f8.png)

Gently pull the belt out the back of the front idler. This will pull the GT2 idler into place.

![Fusion360_r93V2uPN1i](https://user-images.githubusercontent.com/11861478/198882958-d4fadcef-a16f-4a0a-880b-29dff531e744.png)

Temporarily insert a M5x50 SHCS through the front idler (without the tensioner arm in place) to hold the GT2 pulley

![Fusion360_IgsPVKHUWK](https://user-images.githubusercontent.com/11861478/198883011-9e74457b-4ff9-4232-ad4f-1c0365053f4c.png)

Take the belt closest to the 2020 Y extrusion, and feed it into the rear drive module. If you combine pressure and turning the GT2 pulley by hand, the belt will naturally follow the 3d printed surface and come out the other side. Make sure that belt is not twisted from the front toothed pulley all the way to the Y motor toothed pulley.

![Fusion360_UmFg2cfLE5](https://user-images.githubusercontent.com/11861478/198883128-6e1c9a27-623f-4e71-9fc4-a2dac191967e.png)

Flip the left XY joint mid piece over so that you can see the toothed grooves 3d printed into the part.
![Fusion360_vsk3gHWyFN](https://user-images.githubusercontent.com/11861478/198883208-74c20dbc-5478-494e-8574-ca570fae50f5.png)
![Fusion360_hWV8ZlinC8](https://user-images.githubusercontent.com/11861478/198883309-28b60e8c-98c3-4184-b8e5-ec315b0b14ef.png)

For the "free" end of your GT2 belt, make sure it's trimmed cleanly at a 90 degree angle. Insert it into the part so that it overlaps the hole in the belt path. This hole is placed here so that you can push a small screwdriver or hex/allen key through it and push the belt out of the printed channel. 

![Fusion360_kDndSNLoMT](https://user-images.githubusercontent.com/11861478/198883593-74143041-a85a-4421-b63e-a1590e40e00c.png)

With the long end of your GT2 belt, pull it tight and try to remove any obvious slack in the system. **Make sure that your front Y toothed pulley has the M5x50 SHCS through it to hold it into place, or you will cut your belt too short at this step!!**. Cut your belt so that it fits in the other slot in the printed part, similar to the red line in the image above. 

Flip the 3d printed part over, and snap it into the XY Joint Lower piece:

![Fusion360_Hjc4LBXLTz](https://user-images.githubusercontent.com/11861478/198883880-f775db32-cf5a-438f-a87b-00a002f386fd.png)

Make sure that the belts are oriented as follows. The "free" end of the Y belt will slide in a channel between the MGN9 carriage and the XY joint.

![Fusion360_xVrUfiISvt](https://user-images.githubusercontent.com/11861478/198883864-a6442f42-718a-4c3c-a05d-16c64e840801.png)

Manually pull the M5x50 SHCS screw forward in the Front Idler, and make sure the Y belt can be tensioned without too much front idler movement. If there is a lot of slack in the belt, consider trimming the belt one tooth shorter at a time until there's not much extra slack. As a tip--you can remove the M5x50 SHCS while installing the belt into the toothed slot to make it easier.

Once you are confident with the Y belt length, remove the Y belt, cut another Y belt of identical length, and then install both Y belts in the system. **Do not fully install the Y tensioner yet--just keep the M5x50 SHCS holding the GT2 idler**.

## Part 5: X Axis

Install the X axis MGN12 rail onto the 2020 extrusion. Install Tnuts as needed (2 M5 per side on top, 1 M3 per side on bottom) and screw the X axis to the partially assembled XY joint using a M3x20 from the bottom of the XY joint:

![Fusion360_LfYs2FOs7U](https://user-images.githubusercontent.com/11861478/198884492-e319640d-d1b4-4ce8-b014-dd50eba783fe.png)

Insert a M5x40 SHCS with washer/bearing/bearing/washer into the left XY joint:
![Fusion360_kSubw5IJT0](https://user-images.githubusercontent.com/11861478/198884731-be100bc8-abb4-4372-a8c6-79f2d4b10549.png)

Then install the XY joint upper on top. Insert the additional M5x40 SHCS, hexnuts, and GT2 20T idler:

![Fusion360_KyqO03vBuD](https://user-images.githubusercontent.com/11861478/198884905-1c568a20-6a1d-48a7-b67f-d6af64c5ccd2.png)

On the right XY joint, install the XY joint upper with M5x40, washer/bearing/bearing/washer onto the lower/mid XY joint parts. Install the rest of the M5x40 screws, as well as the GT2 20T idler. 

![Fusion360_0UUWuQsBGq](https://user-images.githubusercontent.com/11861478/198885080-58bc8513-9279-406d-9c8f-5e26900034f8.png)

## Part 6: X Belts

In preparation for the X belts, install heatset inserts into the X carriages, and install the T0 X endstop into the left carriage. Do not install bolts through the X carriage yet--it is easier to install the belts with the X carriages as two separate halves.

Route an initial X belt by inserting the ends of the belts into the opening above the X pulley, fishing through the slots in the back of the drive module. 

![Fusion360_TNfg9VQteW](https://user-images.githubusercontent.com/11861478/198885244-51033238-85ab-4f9a-b723-cae52abad99b.png)
![Fusion360_Z8PnJcnRFt](https://user-images.githubusercontent.com/11861478/198885421-cba22325-443c-4cd1-b95c-b0081dbf400f.png)

The X belt routing is similar to a standard CoreXY belt routing, except upper belt attaches to the left X carriage (T1), and the lower belt attaches to the right X carriage (T1). 
![Fusion360_s94B1QZMBw](https://user-images.githubusercontent.com/11861478/198885482-35005ae1-c778-4cac-900c-2c62144a22fa.png)

Since the front tensioner Y accent pieces are not installed, it should be easier to route the X belts through the tensioner body. 

![Fusion360_Zz1pREp1Aq](https://user-images.githubusercontent.com/11861478/198885756-a158b78c-02b9-44d6-b076-436fe363f9a9.png)

Once the belt is routed, temporarily install an X carriage and pull the X axis flush to the front of the printer, to make sure there is enough belt length. You can leave an inch or two extra belt sticking out of the X carriage if needed

Cut the X belt, and then remove, and cut another X belt exactly the same length. Install both belts, making sure that both have the same amount of extra belt length extending from the X carriages. With this complete, install the M3x30 bolts through the X carriages to make sure both halves are fully secured. 

Remove the M5x50 SHCS from the front Y idler pulleys, and finally install the Y tensioners and tensioning screws
![Fusion360_ggaEBeqQwN](https://user-images.githubusercontent.com/11861478/198885860-28b379fd-eb42-4385-8554-9b05e671ccc9.png)

If you have difficulty aligning the 20T toothed idler with the M5x50 screw, use an allen key or small screwdriver to push it backwards from the bottom while you insert the M5x50 back in from the top.

## Part 7: Tensioning and Alignment

With all belts installed, double check all belt routing to make sure belts are fully seated on their bearings/pulleys. 

Push the X axis backwards so it's about 3/4 of the way to the back of the printer. Pluck the Y belts (between the XY joints and front idlers) and tension them until there is a clear low bass tone, even on both sides. My printer is currently around 60Hz at about Y=200mm, but this is not scientific. Pluck the X belts and tension them so they match the same tone. Push the X axis backwards and check to see if both Y endstops trigger at the same time--if they do not, slightly tweak the X belt tension until they do. If they don't reliably trigger, install the "Y Endstop Bumpers" (not yet designed) to improve Y endstop performance. 

Check all belt tensions again once both Y endstops are triggering at the same time. If the belt tensions are significantly different between X1/X2, loosen the screws connecting the X axis extrusion to the XY joints, recheck Y endstop triggering/belts, and once belt tension is the same across all belts and the Y endstops trigger at the same time, tighten the X axis 2020/XY joints for a final time. Check all structural bolts through the gantry to make sure they are moderately tight. DO NOT OVERTIGHTEN, just snug: M5x30 BHCS on Drive Modules (idler pulley axles), M5x40 SHCS holding idler pulleys on XY joints, M5x50 SHCS on Front Idler tensioners.

Later on, recheck belt tensions once the printer has homed XY and stepper motors are engaged.

## Part 8: Nozzle Wiper Assembly

Take the nozzle wiper components and insert two heatsets into the ends of each nozzle wiper body. Cut pieces of silicone wiper (based on template) and insert into the slots. Secure silicone pieces with M3x20 SHCS to the end of the wiper body. To mount the wiper assembly to the bottom of the XY joint, note that two of the XY Joint Lower to MGN9 Y rail screws have passthroughs in the nozzle wiper body, and two will be used to mount. Remove the two M3x16 SHCS screws (diagonally) where the nozzle wiper will mount to the XY Joint Lower, and put M3x20 SHCS through the nozzle wiper body, thorugh the XY Joint Lower, and into the MGN9 carriage. Tighten securely, and repeat with both sides.

## Part 9: Toolhead Assembly

Assemble two CW2 modules per the standard CW2 instructions. Mount your choice of CAN control board to the back/sides based on the model. NEMA14 sized CAN boards can be mounted with M3 brass standoffs off the NEMA14 motor, HUVUDs/NEMA17 can be mounted with an arm that replaces the cable chain mount. Stealthburner style CAN boards can be installed integrated into the body of the Stealthburner/CW2. 

For the T0 toolhead (left), print the specific toolhead_rear component in the Tridex repo along with the standard toolhead_front from the stealthburner repo. This modified toolhead_rear has a bumper extension that will allow T1 to home off of it. Note--this toolhead_rear part requires supports at this time. 

For the T1 toolhead (right), print the standard toolhead_front and toolhead_rear from the Stealthburner repo, along with the custom X endstop mount from the Tridex repo. Mount a microswitch with lever into the X endstop mount, with wire leads extending through the toolhead_rear mount behind the hotend heatsink, where the wires will join the rest of the hotend thermistor/heater wires to travel up to CW2. Mount the X endstop mount to the toolhead body with M3 screws into the heatset inserts in the toolhead body.

![image](https://user-images.githubusercontent.com/11861478/200189629-fee2292a-66cb-4d75-bcb7-f635301dcd81.png)

For the T1 toolhead (right), print the standard toolhead_front and toolhead_rear from the Stealthburner repo, along with the custom X endstop mount from the Tridex repo. Mount a microswitch with lever into the X endstop mount, with wire leads extending through the toolhead_rear mount behind the hotend heatsink, where the wires will join the rest of the hotend thermistor/heater wires to travel up to CW2. Mount the X endstop mount to the toolhead body with M3 screws into the heatset inserts in the toolhead body.![image](https://user-images.githubusercontent.com/11861478/200189609-e5aad198-f358-4d96-b6a8-331558a798df.png)

For the T1 toolhead (right), print the standard toolhead_front and toolhead_rear from the Stealthburner repo, along with the custom X endstop mount from the Tridex repo. Mount a microswitch with lever into the X endstop mount, with wire leads extending through the toolhead_rear mount behind the hotend heatsink, where the wires will join the rest of the hotend thermistor/heater wires to travel up to CW2. Mount the X endstop mount to the toolhead body with M3 screws into the heatset inserts in the toolhead body.

Assemble the Stealthburner fan assembly per the standard instructions. Double check the X carriage is sitting flush/properly with the MGN12H rail and all screws are tight--if it is not, it will create large offsets between the toolheads. Mount the CW2, Toolhead, and Stealthburner onto the X carriage, and tighten securely. Make sure any extra 2GT belt does not get pinched between the toolhead body and the X carriage, since this will create large offsets. 
