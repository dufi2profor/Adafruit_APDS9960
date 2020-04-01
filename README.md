# Adafruit APDS9960 Library [![Build Status](https://travis-ci.com/adafruit/Adafruit_APDS9960.svg?branch=master)](https://travis-ci.com/adafruit/Adafruit_APDS9960)

<a href="https://www.adafruit.com/product/3595"><img src="assets/board.jpg?raw=true" width="500px"></a>

This is the Adafruit APDS9960 Proximity, Light, RGB, and Gesture sensor Library

Tested and works great with the Adafruit APDS9960 Board 
* http://www.adafruit.com/products/3595

This chip uses I2C to communicate, 2 pins are required to interface

Adafruit invests time and resources providing this open source code, please support Adafruit and open-source hardware by purchasing products from Adafruit!

Written by Dean Miller, Limor Fried for Adafruit Industries.  
BSD license, check license.txt for more information
All text above must be included in any redistribution

To install, use the Arduino Library Manager and search for "Adafruit APDS9960 Library" and install the library.

Added some functions for gesture reading, original readGesture() after first gesture detected did not exit the mode in sensor thus kept reading FIFO. delay(30) blocked the mani loop as well. New function checkGesture() can be placed in loop() and will call readGestureNonBlocking() every 10 ms, or readGestureNonBlocking() can be called withing some reasonable short intervals. Running i2c at 100 kHz it will take around 4 to 5 ms for one read cycle from sensor. Running i2c at 400 kHz this time is shorten.
Added also support for Teensy boards.
