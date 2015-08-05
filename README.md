# Electron

The Electron is a tiny cellular development kit based around U-Blox's SARA U-series (3G) or G-series (2G) cellular modem module and a STM32F205 ARM Cortex M3 microcontroller.

The Electron has a footprint which is a drop-in compatible with the Particle Photon or Core.

Compared to the Particle Photon, the Electron introduces additional hardware features and changes:

1. JST LiPo battery connector.
2. Switch-mode battery charge management and system power path management circuit.
3. Fuel gauge circuit for lithium batteries.
4. Nano-SIM connector.
5. Access to USB data lines. 
6. 12 additional GPIO Pins.
7. 4 additional ADC channels.
8. 6 Timer channels exposed.
9. 2 additional UART peripherals.
10. 1 additional SPI and CAN peripheral.

A detailed description of the pin mapping can be found in **electron-pinmap_v1** spreadsheet.
* Sheet 1: Overview of the Electron pin-out.
* Sheet 2: Overview of the Photon pin-out for comparison.

### Pin Descriptions:
- **VIN:** This is the power supply pin to the Electron with a voltage range of 3.6 to 5.5VDC (internally regulated down to 3.3VDC). When the Electron is powered via its USB port, this pin will *ouput* a voltage of approximately 4.7VDC. Why 4.7 and not 5? Well, the actual voltage will be the USB voltage, which is normally 5, minus the forward voltage drop (0.3V) of the protection diode.
- **RST:** This is an active-low reset pin for the Electron.
- **VBAT:** Supply to the internal RTC, backup registers and SRAM (1.8 to 3.3VDC).
- **3V3:** This pin is the output of the on-board regulator. When powering the Photon via VIN or the USB port, this pin will *output* a voltage of 3.3VDC.
- **WKP:** This is an active-high input that allows you to wakeup the module from sleep/deep sleep modes. When not used as a WAKEUP, this pin can also be used as a digital GPIO, ADC input or PWM.
- **A0 - A5:** These can be used as digital GPIOs, ADC inputs. Alternate functions include: SPI, PWM and DAC.
- **B0 - B5:** These can be used as digital GPIOs, partial ADC inputs, partial PWM outputs.
- **C0 - C5:** These can be used as digital GPIOs.
- **D0 - D7:** These can be used as digital GPIOs. Alternate functions include: UART, SPI, I2C, PWM and CAN. 
- **DAC:** This pin can be used as a digital GPIO, ADC input or as a DAC ouput.
- **RX:** Primarily used as UART RX, but can also be used as a digital GPIO, ADC input or PWM.
- **TX:** Primarily used as UART TX, but can also be used as a digital GPIO, ADC input or PWM.

Please review the pinmap spreadsheet to better understand the alternate functions of the GPIO pins.

### Eagle (schematic, pcb layout and drc):
**eagle** contains the history of Electron designs and **cell_v010** is the latest design folder and **cell_v011** is currently "work in progress" which will incorporate various peer review changes, community suggestions, minor updates and then released as the next revision. 

#License

Designed by Particle. Distributed under a Creative Commons Attribution, Share-Alike license.
Development kits based on this product should be distributed under a similar license.
Commercial products using the Electron as a reference design need not comply with this license; further questions can be sent to hello@particle.io.
Check license.txt for more information.
