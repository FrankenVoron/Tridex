# Tridex
This modification is based on the official Voron Trident release files: https://github.com/VoronDesign/Voron-Trident/releases/tag/Trident

It adds:
-350x250mm frame for use with 250x250mm build plate
-IDEX toolheads
-2040/4040 frame with EZBake front door for additional insulation
-Updated front skirt files for flush appearance with door

All files are in "alpha" state--functional, but not optimized. Use them at your own risk, no support is implied :) 

![Fusion360_BgZ3UrNNhE](https://user-images.githubusercontent.com/11861478/147276308-37a7ae89-d276-4e3b-b2ec-65ea3f8aff72.png)

Needed for conversion from stock Trident (250x250):
-Additional extrusions
-MGN12 rail (400mm long) with dual MGN12H carriages
-4 NEMA14 motors for XY (similar to V0.1 XY motors)
-New Gates belts (4 total)
-2 GT2 20T idlers (not genuine Gates type--they are too tall), 2 GT2 20T pulleys
-2 Huvud CAN Toolhead boards
-1 CAN adapter for Raspberry Pi (such as Waveshare)
-1 complete additional toolhead in parts
-Control board capable of driving 7 motors (2 Y, 2 X, 3 Z)
