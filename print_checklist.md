Check list for print on RepRapPro Ormerod
=========================================

Check GCode file 
----------------

We use pronterface to set temperature for bed and hot end. Like it, it's more 
easy to change it. So it's important to don't have temperature command like M104
or M140 in gcode.

Heating up
----------

Set printer T value in pronterface.

PLA : 

  BED: 85 &deg;C or +

  HOT-END: 195 &deg;C or +

This value can change (measure accuracy or plastic type).

Homing
------

Use automatic homing for X and Y axe : 

    G28 X50 Y50 ; homing X and Y
    G0 X50 Y50  ; set pos for Z homing

Z automatic homing is unsecure so do it manualy at pos X50 Y50 :
Use pronterface to make small step on Z axis. Set a paper between nozzle and
bed, the paper must move with a small resistance when Z is homing.

Make a :

    G92 Z0 ; set 0 for axe Z.

Check value you must have :

    M114 ;must return X=50 Y=50 Z=0

Set the bed level compensation
------------------------------

More info on [RepRapPro web site](http://www.reprappro.com/documentation/ormerod/axis-compensation/#Bed_Plane_Compensation). 

Print "setbed.g" from SD card

Upload file
-----------

Print from serial is unsafe (timing issue). So we must to upload G code to SD 
card and print from them.

Open the G code in pronterface with "load file" button. After a few second, the 
layers are display on yellow plate (gcode view).

Click on "SD" -> upload, you must set a "8.3" filename for your gcode.

The upload can take a while (serial is at 115200 bauds), so be patient.

Launch print job
----------------

Use "SD" button then print and choose your gcode file. 

 

