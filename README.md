# mosquitto_rio

This is the MQTT software mosquitto compiled for the RoboRIO.

The FRC tools were used to cross-compile the code for the 'RIO.

Details of the changes from the standard mosquitto download:

Updated config.mk while compiling to remove features that wouldn't compile easily

Mostly unneeded features, such as TLS
Should check, probably others that could be removed

Updated Makefiles for cross-compiling
In general, command substitutions for ${CC}, ${CXX}, ${STRIP} prefixed with ${CROSS_COMPILE}
Checked for ${AR} and ${LD}, but did not find any

A couple of "cc"s were converted to "gcc"

For the install step, used a different destination directory:
$ make DESTDIR=$PWD/_install install

The _install directory now contains the files to copy to the RoboRIO

Basic instructions came from here:
https://dev.eclipse.org/mhonarc/lists/mosquitto-dev/msg00057.h

One of the developers had put in updates as described here:
https://dev.eclipse.org/mhonarc/lists/mosquitto-dev/msg0010

But not completely.  Thus the changes described above.

## Install lib in RoboRio Development Environment

According to commit from Endeavor in 2018:
Ended up putting libmosquitto.a (from mosquitto-rio) in ~/wpilib/user/cpp/lib, which is where the CTRE libs are located
Project settings update:
- Removed Endeavor/lib/ and removed it from library paths - not needed
- Added "mosquitto" to libraries

libmosquitto.a is in this repository in mosquitto-1.4.11/lib
For 2019, copy this file to frc2019/roborio/lib

Also, add mosquitto.h (from lib directory above) to project
