## XCAN firmware for STM32F042 based boards

![build workflow](https://github.com/moonglow/pcan_cantact/actions/workflows/firmware_build.yml/badge.svg)

## Target Hardware

* [CANtact](https://github.com/linklayer/cantact-hw) - opensource USB-CAN adapter project `make cantact_16`
* [CANable](https://canable.io/) - opensource USB-CAN adapter based on CANtact project `make canable`
* [Entreé](https://github.com/tuna-f1sh/entree) - opensource USB-C CAN adapter based on CANable project `make entree`
* [Ollie](https://github.com/slimelec/ollie-hw) - opensource USB-CAN adapter with isolated USB `make ollie`
* Any other STM32F042 based boards with external or internal OSC.

## Toolchain

* GNU Arm Embedded Toolchain

## Fedora 

    gh repo clone codebuk/pcan_cantact
    cd pcan_cantact/
    make
    ls build-canable
    # USB device will change - this was for as shipped canable
    sudo dfu-util -d 0483:df11 -c 1 -i 0 -a 0 -s 0x08000000 -D ./build-canable/pcan_canable_hw.bin
