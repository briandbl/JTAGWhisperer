The JTAG Whisperer
==================

With this library, your Arduino is an XSVF player. Use it to program CPLDs and FPGAs!

Instructions
============

1. Find your Arduino IDE's sketches directory. This is the directory where you keep your own sketches.

1. If there isn't already one, create a `libraries` directory inside the sketches directory.

1. Unzip the project archive into `libraries`. It should end up looking like this: `[Your Arduino sketches directory]/libraries/JTAGWhisperer/JTAGWhisperer.h (etc.)`

1. Restart your Arduino IDE and you should see JTAGWhisperer among the libraries in the Sketch -> Import Library... menu.

1. Open the example JTAGWhisperer sketch. Upload it to your Arduino.

1. Get a Xilinx XC9572XL CPLD. Hook up your CPLD's JTAG pins to the Arduino: pins 8, 9, 10, 11 to TMS, TDI, TDO, and TCK, respectively. (If you have TCK on pin 11, you probably did it right.)

1. Apply power to the CPLD (note that it's a 3.3-volt device!). Try asking it its device ID as follows, from the root of the source directory:

`./send_xsvf -p /dev/tty.your_arduino_serial_port xsvf/XC9572XL/DeviceID.xsvf`

1. You should see a back-and-forth that ends up with a "Success" message. If you rebuild the sketch with the DEBUG messages enabled in SerialComm.h, you'll see the actual device ID that's reported.

Generate your own XSVF files using Xilinx iMPACT, or download them from the web. Just make sure they're for your device.

Credits
=======

By [Mike Tsao](http://www.sowbug.com/). Project on [GitHub](https://github.com/sowbug/JTAGWhisperer/).

Many thanks to [Ben](https://github.com/ben0109/XSVF-Player/), who adapted the Xilinx XAPP058 code into something comprehensible. This code evolved from his project, and all the clever parts are his.
