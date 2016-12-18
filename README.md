# Library: XPT2046 Touchscreen with Calibration

XPT2046_Touchscreen_calibrated is a clone of Paul Stoffregen's excellent library for the XPT2046 touch controller at https://github.com/PaulStoffregen/XPT2046_Touchscreen. It adds a calibrate function to convert touch screen coordinates to pixel values. 

![XPT2046 Touch Calibration](http://www.ars-informatica.ca/eclectic/wp-content/uploads/2016/12/touch-calibration2.jpg) ![XPT2046 Touch Calibration Parameters](http://www.ars-informatica.ca/eclectic/wp-content/uploads/2016/12/touch-calibration3.jpg)

Sample sketches are for the Digistump Oak. Both should be easily adapted to other Arduino-type processors. Sketch touch_XPT2046_digistump_oak.ino, as is, displays raw touch values. Uncomment the 

    //  ts.calibrate(-.00114, -.0653, 254, -.0885, -.00125, 348, 320, 240, 1);

line and it will now show pixel coordinates. The calibration parameters above are particular to my test screen, but may work with other screens using the ILI9341 and XPT2046 controllers.

Usage: the first six parameters are the calibration values we get from touch_XPT2046_digistump_oak_calibration, and the next two are the screen width and height in the screen orientation you will be using. The final optional parameter sets the screen rotation; 0 gives the original unrotated orientation, 1 defines a 90 degree counter-clockwise rotation, 2 defines 180 degrees counter-clockwise, and 3 is 270 degrees. This matches most screens with most graphics libraries - but not all. Please check.

The Oak's version of SPI.cpp may be out of date, and may cause erroneous values. See more at http://www.ars-informatica.ca/eclectic/digistump-oak-with-a-touch-enabled-display-screen-circuit-and-code/. The entire project is described starting at http://www.ars-informatica.ca/eclectic/tutorial-digistump-oak-with-a-touch-enabled-display-screen/. 

Three-point calibration has been implemented using Fang and Chang's [u]Calibration in touch-screen systems[/u], http://www.ti.com/lit/an/slyt277/slyt277.pdf, Analog Applications Journal, 2007.

The modified software is released under the same conditions as the original. Feel free to modify, share, etc.

See Paul's original version for further documentation.

