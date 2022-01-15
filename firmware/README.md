# MMDVM Firmware
These binaries are compiled using the sources available from here: https://github.com/G4KLX/MMDVM

New binaries are compiled and pushed to git each day the source repositories are changed.

ZUM Radio-MMDVM 0.9

    stm32flash -i 20,-21,21:-20,21 /dev/ttyAMA0
    stm32flash -v -w ZUM_Radio-MMDVM_0.9.bin -g 0x0 -R /dev/ttyAMA0

ZUM Radio-MMDVM 1.0

    stm32flash -i 20,-21,21:-20,21 /dev/ttyAMA0
    stm32flash -v -w ZUM_Radio-MMDVM_1.0.bin -g 0x0 -R /dev/ttyAMA0

