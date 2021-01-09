# STM32 Sandbox
### Bare Metal STM32 Sandbox Template

STM32 microcontroller template for use with a standard build environment. Does not use any IDE's etc, allowing you to inspect what's going on and learn from it.

The example included in this repository is configured for the STM32F103C8T6 "Blue Pill" device. It blinks the onboard LED (PC13) periodically.

## Prerequisites:
- [STM32Cube MCU Package](https://www.st.com/en/embedded-software/stm32cube-mcu-mpu-packages.html)
    - Requires a sign-in to ST in order to download.
- ARM embedded toolchain
    - On x86_64 Fedora, run `sudo dnf install arm-none-eabi-gcc arm-none-eabi-binutils arm-none-eabi-newlib` (installs a cross-compilation toolchain).
- STLink flashing tool
    - On x86_64 Fedora, run `sudo dnf install stlink`.
- GNU Make
    - On x86_64 Fedora, run `sudo dnf install make`.
- tr
    - On x86_64 Fedora, run `sudo dnf install coreutils` (most likely already installed).

## Usage
1. Extract the STM32Cube MCU package, and update the `CUBE_PATH` variable to point to it.
2. Ensure all other variables in the Makefile are correct (example is configured already for the "Blue Pill" MCU).
3. Run `make hal_config` to initialize the HAL configuration file (placed in the CONFIG_DIR directory), then enable/disable only the drivers listed in the `HAL_DRIVERS` variable within the Makefile. See HAL Config below for the exact list if building the sandbox as is.
3. Run `make` to build the program binary, ready to be uploaded to the STM32 device.
4. Run `make flash` to flash the binary.

## Resources
[STM32F1 Series Portal](https://www.st.com/en/microcontrollers-microprocessors/stm32f1-series.html)

[STM32F103C8 ("Blue Pill") Portal](https://www.st.com/en/microcontrollers-microprocessors/stm32f103c8.html)

[STM32CubeF1 Portal](https://www.st.com/en/embedded-software/stm32cubef1.html)  
(Be sure to see "UM1850 Description of STM32F1 HAL and low-layer drivers 3.0" for the user manual on the HAL layer)

[STM32F103C8T6 ("Blue Pill") Datasheet](https://components101.com/microcontrollers/stm32f103c8t8-blue-pill-development-board)

[Makefile Tutorial/Cheatsheet](https://makefiletutorial.com)

[STM32-base Guide](https://github.com/STM32-base/STM32-base)  
(Parts of this adapted from here)

[Bare Metal Programming Introduction](https://interrupt.memfault.com/blog/zero-to-main-1)

## HAL Config
If building the sandbox as is, copy the following and replace the "Module Selection" block with the following. All other drivers/modules should be commented out.

```
#define HAL_MODULE_ENABLED
#define HAL_CORTEX_MODULE_ENABLED
#define HAL_FLASH_MODULE_ENABLED
#define HAL_GPIO_MODULE_ENABLED
#define HAL_RCC_MODULE_ENABLED
```
