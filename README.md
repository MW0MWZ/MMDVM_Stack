# MMDVM Software Stack
This software has been built on arm32v6 arch (armhf) on Alpine Linux.
It can be used in docker, or directly on Alpine Linux hosts.

You will need some basic libraries installed, you can do that with the below command.
apk --no-cache add libgcc libstdc++ wxgtk-base libusb alsa-lib wiringpi i2c-tools

These binaries are compiled using the sources available from here: https://github.com/g4klx and here: https://github.com/juribeparada

New binaries are compiled and pushed to git each day the source repositories are changed.
