# Sigfox Protocol Physical Layer for S2-LP - Demo for STM32L0

`renard-phy-s2lp-demo-stm32` is a STM32L0 demo application for the open source Sigfox PHY layer [`renard-phy-s2lp`](https://github.com/Jeija/renard-phy-s2lp), which interfaces with STMicroelectronics' S2-LP ultra-low power transceiver chip.

It combines [`renard-phy-s2lp`](https://github.com/Jeija/renard-phy-s2lp) and renard-phy-s2lp's STM32L0 hardware abstraction layer [`renard-phy-s2lp-hal-stm32`](https://github.com/Jeija/renard-phy-s2lp-hal-stm32).

## Building
### Clone
Make sure to clone this repository recursively so that all submodules get downloaded as well:
```
git clone --recursive https://github.com/Jeija/renard-phy-s2lp-demo-stm32/
```

If you forgot `--recursive` while cloning, you can also use the following command to initialize all submodules:
```
git submodule update --init --recursive
```

### Configure
See [`renard-phy-s2lp-hal-stm32`](https://github.com/Jeija/renard-phy-s2lp-hal-stm32) for information on the default pin configuration and on how to change it.

Edit `src/main.c` to set your Sigfox credentials (device ID, Network Authentication Key and payload).

### Compile
Make sure you have [`stlink`](https://github.com/texane/stlink) and the GNU ARM Toolchain (`arm-none-eabi`) installed. To compile and flash this demo application, use:

```
make
make stlink-flash
```

## Usage
`renard-phy-s2lp-demo-stm32` was tested with the [STEVAL-FKI868V2](https://www.st.com/en/evaluation-tools/steval-fki868v2.html) evaluation kit, which is based on a NUCLEO-L053R8 development board. It transmits a Sigfox uplink whenever the blue `USER` button is pressed (modify `src/button.c` or `src/main.c` to change this behaviour). It then waits for a downlink and outputs the received downlink frame on the serial console. Watch the serial console for debug output.

## Licensing
`renard-phy-s2lp-demo-stm32` is licensed under the MIT License. See `LICENSE` for details.