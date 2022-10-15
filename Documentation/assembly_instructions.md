# Assembly Guide for Tridex Gantry

This guide is meant to be a supplement to the standard Voron Trident and Voron Stealthburner/CW2 assembly manuals. It is not official, or final, but hopefully it will help you figure out the order of operations and make life a little bit simpler!

## Part 1: Basic Assembly

Follow the Trident manual, skipping the Front Idler, A/B Drive, and X Axis assembly. You may mount the entire Z assembly including the deck panel, bed, and electronics, and remake the CW2 and Stealthburner fan assemblies per the Stealthburner manual. Mount the Y MGN9 rails to the Y extrusions, but leave the screws loose so that they can slide slightly back and forth.

## Part 2: Drive Modules

Prepare for drive module assembly by soldering wire leads to the Y microswitches, and mounting each switch to the accent piece. Route the wire leads through the hole in the drive module lowers. Mount the pulleys to all 4 motors using the alignment jig. Secure the Y motors to the drive module lowers by screwing M3xXX screws through the lower and the motor mounts, fully tightening as there will not be access to these screws later. Press the upper and lower drive module pieces into the mid accent piece, making sure the wire routing for the Y endstops is still correct. Position the X motor in place, making sure the endstop wires align in the channel. Partially screw in the M3x30mm screws to hold the X motor in place. 

Once both drive modules are assembled, mount to the printer by sliding onto the Y extrusion, and pressing backwards into the rear vertical extrusions. Note--if you cannot get the drive modules to fit due to interference with the MGN9 Y rails, loosen the MGN9 rail and slide forward slightly to give clearance. Insert the rear crossbar extrusion between the drive modules, and check drive modules, etc for alignment. Install screws for the bottom of the drive modules into the Y and vertical extrusions first, lightly tightening, and checking for alignment before fully tightening down. 

Once the drive modules are fully installed, install mounting brackets between the rear crossbar and rear center Z extrusion. Slide the MGN9 Y rails backwards until they touch the drive modules, then use the MGN9 3d printed alignment tools to make sure the Y rails are centered and tighten down.

## Part 3: Front Idlers

Assemble the front idlers with only the X tensioners (note the markings - LX for left X, and RX for right X tensioner) + washer/bearing/bearing/washer stack, using the same assembly method used for standard Voron Trident front idlers. Keep the M5x50mm bolt partially loose, so the front idler halves can flex slightly when you slide it onto the Y extrusion slots. The tabs on the idlers should fit in the vertical extrusions. Lightly snug the M5x10 and M5x16 bolts on the bottom of the front idler, making sure the idler contacts both the Y and vertical extrusions, then tighten completely. Secure the top half of the idlers to the Y extrusion with 2x M5x10 BHCS. 

## Part 4: XY Joints/Y Belts

Unlike standard Voron Trident XY joint assemblies, the Tridex XY joints must be assembled on the printer in stages. Mount the XY joint lowers to the MGN9 Y rails. Route a Y belt around the Y motor/pulley, then through the front idler, inserting the GT2 pulley in the front idler, pulling the belt into place. Temporarily insert the M5x50 screw through the front idler to hold the GT2 pulley in the furthest back position. Take the XY joint mid piece, hold the Y belt tight, and mark where the belt should be to fully insert into both grooves in the 3d printed part. Remove the Y belt, cut Y belt to length, and then cut a second Y belt to an identical length for the other side. Reroute the Y belts on both sides, inserting into the 3d printed parts. If extra slack is needed, remove the M5x50 screw for the GT2 pulley temporarily to allow the pulley to slide backwards slightly. Once the belt is inserted into the XY joint mid part, snap the mid piece onto the XY joint lower, using the locating features to hold it in place. Note, the Y idler tensioner doesn't have to be installed at this point. This will make it easier to route the X belts later.

Install the X axis MGN12 rail onto the 2020 extrusion. Install Tnuts as needed, and screw the X axis to the partially assembled XY joint using a M3x20 from the bottom of the XY joint. Insert a M5x40 SHCS with washer/bearing/bearing/washer into the left XY joint, and then install the XY joint upper on top. Insert the additional M5x40 SHCS and hexnuts, lightly tighten. Install the GT2 20T idler with M5x40, making sure to not tighten the screw, just screw it in until the top of the M5x40 is flush with the top of the XY joint upper.

On the right XY joint, install the XY joint upper with M5x40, washer/bearing/bearing/washer onto the lower/mid XY joint parts. Install the rest of the M5x40 screws, as well as the GT2 20T idler. 

## Part 5: X Belts

In preparation for the X belts, install heatset inserts into the X carriages, and install the T0 X endstop into the left carriage. Do not install bolts through the X carriage yet--it is easier to install the belts with the X carriages as two separate halves.

Route an initial X belt by inserting the ends of the belts into the opening above the X pulley, fishing through the slots in the back of the drive module. The X belt routing is similar to a standard CoreXY belt routing, except upper belt attaches to the left X carriage (T1), and the lower belt attaches to the right X carriage (T1). Since the front tensioner Y accent pieces are not installed, it should be easier to route the X belts through the tensioner body. 

Once the belt is routed, temporarily install an X carriage and pull the X axis flush to the front of the printer, to make sure there is enough belt length. You can leave an inch or two extra belt sticking out from both ends of the belt.

Cut the X belt, and then remove, and cut another X belt exactly the same length. Install both belts, making sure that both have the same amount of extra belt length extending from the X carriages. With this complete, install the M3x30 bolts through the X carriages to make sure both halves are fully secured. 

Remove the M5x50 SHCS from the front Y idler pulleys, and finally install the Y tensioners. If the 20T idlers are offset due to Y belt tension, use an allen key or small screwdriver to push it backwards from the bottom while you insert the M5x50 back in from the top, so the pieces fit together.

## Part 6: Tensioning and Alignment

With all belts installed, push the X axis backwards so it's about 3/4 of the way to the back of the printer. Pluck the Y belts (between the XY joints and front idlers) and tension them until there is a clear low bass tone, even on both sides. Pluck the X belts and tension them so they match the same tone. Push the X axis backwards and check to see if both Y endstops trigger at the same time--if they do not, slightly tweak the X belt tension until they do. If they don't reliably trigger, install the "Y Endstop Bumpers" (not yet designed) to improve Y endstop performance. 

Check all belt tensions again once both Y endstops are triggering at the same time. If the belt tensions are significantly different between X1/X2, loosen the screws connecting the X axis extrusion to the XY joints, recheck Y endstop triggering/belts, and once belt tension is the same across all belts and the Y endstops trigger at the same time, tighten the X axis 2020/XY joints for a final time.