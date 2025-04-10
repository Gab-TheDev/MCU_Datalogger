# MCU_Datalogger
**PCB design of an MCU datalogger**

This project is based on the Data Logger design from KiCad Like a Pro. It involves creating a printed circuit board (PCB) for a microcontroller-based system that records environmental data. The main goal is to design, simulate, and lay out a functional PCB using KiCad, while learning key concepts in schematic capture, component placement, routing, and generating manufacturing files.

The data logger includes a microcontroller, voltage regulation, sensor interfaces (like temperature or humidity sensors), and a method for storing or transmitting data, such as an SD card or serial output. The focus is on building a solid foundation in PCB design practices, including signal integrity, component footprints, and creating a professional-quality layout.

By completing this project, I aim to:
- Gain hands-on experience with KiCad’s schematic and PCB layout tools
- Understand the full workflow from schematic to fabrication
- Apply real-world design constraints (power supply, connectors, etc.)
- Build confidence in creating and testing custom electronics

**COMPONENT DESCRIPTION – ATmega328P based Data Logger**

**ATmega328P-A**
Role: Main microcontroller unit (MCU).
Function: Handles all logic and processing for the data logger. Responsible for reading sensors, managing storage (EEPROM), communicating with the RTC, and executing firmware routines.
Interfaces: Supports I2C, UART, ISCP for embedded systems and data logging.
Clock Input: Works with external crystals (16MHz) for stable timing.

**DS1337S – Real-Time Clock (RTC) – SOIC-8**
Role: Timekeeping chip for timestamping logged data.
Function: Maintains calendar and clock time in the absence of MCU power. Communicates with the MCU over I2C.
Features:
- Battery backup support (via V_BAT)
- 2x programmable square-wave/alarm outputs
- ±2ppm accuracy (with proper crystal)
- Package: SOIC-8 (SOIC127P600X175-8N)

**Battery Connector – PinHeader_1x02_P2.54mm_Vertical**
Role: Backup power source connection for the RTC.
Function: Connects a coin cell battery (e.g., CR2032) to the DS1337’s V_BAT pin to keep time when the main power is off.
Package: Standard 2.54mm pitch, vertical pin header — allows easy external battery hookup or socket

**32.768 kHz Crystal – SMD_5032 (2-Pin)**
Role: Real-Time Clock (RTC) timebase.
Function: Provides a low-frequency clock source for the DS1337 RTC module to maintain accurate timekeeping with minimal power consumption.
Typical Use: Used for generating 1-second ticks or sub-second timing in RTC chips.
Package: SMD 5.0 x 3.2 mm, hand-solderable.

**32.768 kHz Crystal – SMD_5032 (2-Pin)**
Role: Real-Time Clock (RTC) timebase.
Function: Provides a low-frequency clock source for the DS1337 RTC module to maintain accurate timekeeping with minimal power consumption.
Typical Use: Used for generating 1-second ticks or sub-second timing in RTC chips.
Package: SMD 5.0 x 3.2 mm, hand-solderable footprint.

**24LC1025 – 128 Kbits I²C EEPROM (SOIC-8 Package)**
Role: Non-volatile EEPROM used for persistent data storage in embedded systems. It ensures data retention even when powered off, making it ideal for data logging, configuration storage, and device identification.
Function: It communicates via the I2C protocol and provides 128 Kbits of storage. Data can be written and read by the microcontroller, with the memory content preserved during power loss.
Package: SOIC-8 5.3 x 5.3 mm with a pin pitch of 1.27 mm

**CONCLUSION:**
The MCU Data Logger project is a complete end-to-end solution for building an embedded system that can collect, process, and store data for later analysis. By utilizing KiCad for designing the schematic and PCB, this project serves as both a practical tool and a learning experience for those interested in embedded systems, sensor interfacing, and PCB design.

This repository aims to serve as a valuable resource for developers and hobbyists looking to create reliable and efficient data logging systems, contributing to the growing community of open-source embedded system designs.

## License
This project is licensed under the MIT License - see the LICENSE file for details
