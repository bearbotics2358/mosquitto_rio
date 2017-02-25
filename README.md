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
