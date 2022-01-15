# MMDVM Firmware
These binaries are compiled using the sources available from here: https://github.com/G4KLX/MMDVM

New binaries are compiled and pushed to git each day the source repositories are changed.

Please remember to set your "UARTSpeed" to the correct value (probably 460800, except for older  
lower spec boards like the Repeater-Builder V1 and V2 that run at 115200)  
in the expert editor: http://pi-star/admin/expert/edit_mmdvmhost.php

** Note - these firmwares should be concidered ALPHA release / un-tested currently,  
this is very early in the test phase, these are not likly to brick your modem, but  
they are only to be used at YOUR risk.

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

    /usr/local/bin/stm32flash -v -w ZUM_Radio-MMDVM_0.9.bin -g 0x0 -R -i 20,-21,21:-20,21 /dev/ttyAMA0
    /usr/local/sbin/pistar-mmdvmhshatreset

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

    /usr/local/bin/stm32flash -v -w ZUM_Radio-MMDVM_1.0.bin -g 0x0 -R -i 20,-21,21:-20,21 /dev/ttyAMA0
    /usr/local/sbin/pistar-mmdvmhshatreset

Nucleo64 F446RE

    mkdir -p /usr/loca/src
    cd /ust/local/src
    git clone https://github.com/ntfreak/openocd
    cd openocd
    ./bootstrap
    ./configure
    make
    make install

    systemctl stop pistar-watchdog.timer
    systemctl stop pistar-watchdog.service
    systemctl stop mmdvmhost.timer
    systemctl stop mmdvmhost.service

    openocd -f /usr/local/share/openocd/scripts/interface/stlink-v2-1.cfg -f /usr/local/share/openocd/scripts/target/stm32f4x.cfg -c "program F446RE.elf verify reset exit"

Nucleo144 F767ZI

    mkdir -p /usr/loca/src
    cd /ust/local/src
    git clone https://github.com/ntfreak/openocd
    cd openocd
    ./bootstrap
    ./configure
    make
    make install

    systemctl stop pistar-watchdog.timer
    systemctl stop pistar-watchdog.service
    systemctl stop mmdvmhost.timer
    systemctl stop mmdvmhost.service

    openocd -f /usr/local/share/openocd/scripts/interface/stlink-v2-1.cfg -f /usr/local/share/openocd/scripts/target/stm32f7x.cfg -c "program F767ZI.elf verify reset exit"

Repeater-Builder V1 Board

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

    # Pi Hat
    /usr/local/bin/stm32flash -w Repeater-Builder_V1.hex -v /dev/ttyAMA0

    # USB Board
    /usr/local/bin/stm32flash -w Repeater-Builder_V1.hex -v /dev/ttyUSB0

Repeater-Builder V2 Board

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

    # Pi Hat
    /usr/local/bin/stm32flash -w Repeater-Builder_V2.hex -v /dev/ttyAMA0

    # USB Board
    /usr/local/bin/stm32flash -w Repeater-Builder_V2.hex -v /dev/ttyUSB0

Repeater-Builder V3 Board

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

    # Pi Hat
    /usr/local/bin/stm32flash -v -w Repeater-Builder_V3.bin -g 0x0 -R -i 20,-21,21:-20,21 /dev/ttyAMA0
    /usr/local/sbin/pistar-mmdvmhshatreset

    # USB Board
    /usr/local/bin/stm32flash -v -w Repeater-Builder_V3.bin /dev/ttyUSB0

Repeater-Builder V4 Board

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

    # Pi Hat
    /usr/local/bin/stm32flash -v -w Repeater-Builder_V4.bin -g 0x0 -R -i 20,-21,21:-20,21 /dev/ttyAMA0
    /usr/local/sbin/pistar-mmdvmhshatreset

    # USB Board
    /usr/local/bin/stm32flash -v -w Repeater-Builder_V4.bin /dev/ttyUSB0

Repeater-Builder V5 Board

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

    # USB Board
    /usr/local/bin/stm32flash -w Repeater-Builder_V5.bin -S 0x8000000 -R /dev/ttyUSB0

