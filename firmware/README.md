# MMDVM Firmware
These binaries are compiled using the sources available from here: https://github.com/G4KLX/MMDVM

New binaries are compiled and pushed to git each day the source repositories are changed.



ZUM Radio-MMDVM 0.9

    apt-get remove stm32flash

    mkdir -p /usr/loca/src
    cd /ust/local/src
    git clone https://git.code.sf.net/p/stm32flash/code stm32flash
    cd stm32flash
    make
    make install

    systemctl stop pistar-watchdog.timer
    systemctl stop pistar-watchdog.service
    systemctl stop mmdvmhost.timer
    systemctl stop mmdvmhost.service

    /usr/local/bin/stm32flash -i 20,-21,21:-20,21 /dev/ttyAMA0
    /usr/local/bin/stm32flash -v -w ZUM_Radio-MMDVM_0.9.bin -g 0x0 -R /dev/ttyAMA0

ZUM Radio-MMDVM 1.0

    apt-get remove stm32flash

    mkdir -p /usr/loca/src
    cd /ust/local/src
    git clone https://git.code.sf.net/p/stm32flash/code stm32flash
    cd stm32flash
    make
    make install

    systemctl stop pistar-watchdog.timer
    systemctl stop pistar-watchdog.service
    systemctl stop mmdvmhost.timer
    systemctl stop mmdvmhost.service

    /usr/local/bin/stm32flash -i 20,-21,21:-20,21 /dev/ttyAMA0
    /usr/local/bin/stm32flash -v -w ZUM_Radio-MMDVM_1.0.bin -g 0x0 -R /dev/ttyAMA0

Nucleo64 F446RE

    openocd -f /usr/local/share/openocd/scripts/interface/stlink-v2-1.cfg -f /usr/local/share/openocd/scripts/target/stm32f4x.cfg -c "program F446RE.elf verify reset exit"

Nucleo144 F767ZI

    openocd -f /usr/local/share/openocd/scripts/interface/stlink-v2-1.cfg -f /usr/local/share/openocd/scripts/target/stm32f7x.cfg -c "program F767ZI.elf verify reset exit"

