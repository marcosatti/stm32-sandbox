# STM32 Sandbox
## Bare metal STM32 sandbox template
STM32 microcontroller template for use with a standard build environment. Does not use any IDE's etc, allowing you to inspect what's going on.

The example included in this repository is configured for the STM32F103C6T8 "Blue Pill" device. It blinks the onboard LED (PC13) periodically.

### Prerequisites:
- [STM32Cube MCU Package](https://www.st.com/en/embedded-software/stm32cube-mcu-mpu-packages.html)
    - Requires a signin to ST in order to download.
- ARM embedded toolchain
    - On x86_64 Fedora, run `sudo dnf install arm-none-eabi-gcc arm-none-eabi-binutils arm-none-eabi-newlib` (installs a cross-compilation toolchain).
- STLink flashing tool
    - On x86_64 Fedora, run `sudo dnf install stlink`.

### Usage
1. Extract the STM32Cube MCU package, and update the `CUBE_PATH` variable to point to it.
2. Ensure all other variables in the Makefile are correct (example is configured already for the "Blue Pill" MCU).
3. Run `make` to build the program binary, ready to be uploaded to the STM32 device.
4. Run `make flash` to flash the binary.

### Resources
[STM32F1 Series Portal](https://www.st.com/en/microcontrollers-microprocessors/stm32f1-series.html)

[STM32F103C6 ("Blue Pill") Portal](https://www.st.com/en/microcontrollers-microprocessors/stm32f103c6.html)

[STM32CubeF1 Portal](https://www.st.com/en/embedded-software/stm32cubef1.html)  
(Be sure to see "UM1850 Description of STM32F1 HAL and low-layer drivers 3.0" for the user manual on the HAL layer)

[Makefile Tutorial/Cheatsheet](https://makefiletutorial.com)

[STM32-base Guide](https://github.com/STM32-base/STM32-base)

[Bare Metal Programming Introduction](https://interrupt.memfault.com/blog/zero-to-main-1)