# ATmega328P Data Logger PCB

A custom **two-layer embedded data-logger PCB** designed in KiCad around the **ATmega328P** microcontroller.

The board integrates external non-volatile memory, a real-time clock, user/status interfaces, and communication headers to provide a flexible hardware platform for data acquisition and logging applications.

## Project Overview

The board was designed to combine the core hardware required for an embedded data-logging system on a single PCB.

Key functions include:

* ATmega328P microcontroller
* External EEPROM for non-volatile data storage
* Real-Time Clock for timestamping
* I2C, SPI, and UART communication interfaces
* MCU GPIO expansion headers
* Status LEDs and user input
* External power connection
* Manufacturing Gerber and drill outputs

## Hardware Architecture

```text
                   ┌─────────────────┐
                   │    ATmega328P   │
                   └───────┬─────────┘
                           │
          ┌────────────────┼────────────────┐
          │                │                │
          ▼                ▼                ▼
     External EEPROM    DS1337 RTC      I/O Expansion
          │                │         ┌──────┼──────┐
          │                │         │      │      │
         I2C              I2C       UART   SPI    GPIO
```

## Main Components

### ATmega328P

The ATmega328P acts as the main controller of the data-logger board and provides the processing and peripheral interfaces required by the system.

### External EEPROM

The design includes **two 24LC1025 EEPROM devices** to provide additional non-volatile storage for logged data.

The EEPROM devices communicate with the MCU through the I2C interface.

### DS1337 Real-Time Clock

A **DS1337S I2C Real-Time Clock** provides date/time information that can be used to timestamp logged data.

### Communication Interfaces

Dedicated headers expose the MCU communication peripherals:

* **I2C**
* **SPI**
* **UART**

Additional headers expose MCU GPIO from Ports B, C, and D for sensor or peripheral expansion.

## PCB Design

**EDA Tool:** KiCad
**PCB Layers:** 2
**Board Material:** FR-4
**Board Thickness:** 1.6 mm

The design includes:

* Front and back copper routing
* Ground and power distribution
* Through-hole interface connectors
* SMD components
* Silkscreen component identification
* Mounting holes
* Gerber and drill manufacturing outputs

## PCB Layout

![PCB Layout](images/pcb-layout.png)

## 3D View

![PCB 3D Front View](images/pcb-3d-front.png)

![PCB 3D Back View](images/pcb-3d-back.png)

## Expansion Interfaces

The board exposes dedicated connectors for:

| Interface | Purpose                              |
| --------- | ------------------------------------ |
| I2C       | Sensors and external I2C peripherals |
| SPI       | SPI-based sensors/peripherals        |
| UART      | Serial communication and debugging   |
| PORTB     | MCU GPIO expansion                   |
| PORTC     | MCU GPIO expansion                   |
| PORTD     | MCU GPIO expansion                   |

## Repository Structure

```text
ATmega328P-Data-Logger-PCB/
├── hardware/
│   ├── data-logger.kicad_pro
│   ├── data-logger.kicad_sch
│   ├── connectors.kicad_sch
│   └── data-logger.kicad_pcb
├── manufacturing/
│   ├── gerber/
│   └── drill/
├── images/
│   ├── layoyt.png
│   ├── pcb_3d_front.png
│   └── pcb-3d-back.png
├── docs/
│   └── data-logger-project.pdf
└── README.md
```

## Design Outputs

The repository includes the KiCad source files together with Gerber and drill outputs required for PCB fabrication.

## Skills Demonstrated

* Embedded hardware design
* Schematic capture
* PCB layout and routing
* ATmega328P system design
* I2C peripheral integration
* External EEPROM integration
* RTC integration
* UART/SPI/I2C interface breakout
* KiCad
* PCB manufacturing-file generation

## Project Scope

This repository focuses on the **hardware and PCB design** of the data-logger platform.

The project was completed through:

- Schematic capture
- PCB layout and routing
- Gerber generation
- Drill-file generation

The board was **not fabricated or physically validated**.

Firmware for complete data-logging functionality is outside the scope of this repository.
