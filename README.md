# UBC Solar x [**PCBWay**](https://www.pcbway.com/) Sponsorship for Telemetry Board V3 Showcase!
> Below are all the PCBs UBC Solar has sponsored with [**PCBWay**](https://www.pcbway.com/). 
> * ⭐ [**PCBWay**](https://www.pcbway.com/) provides reliable PCB manufacturing and assembly services, offering a wide range of cost-effective options for rapid prototyping and small-volume production. 
> * 🌟 [**PCBWay**](https://www.pcbway.com/) kindly supported all these project with manufacturing and design review! Please visit their site if you need PCB manufacturing or assembly services. 
> * ⭐ There are lots of options for low-cost prototyping and small series production. 
> * 🌟 Their 24/7 support for payments and for reviewing makes our teams production scale rapdiy!

# Author: Jacky Chen (Power and Signals)

# Acknowledgement
I would like to thank PCBWay for sponsoring this board 

# Front Side
<img width="1080" height="1500" alt="image" src="https://github.com/user-attachments/assets/39d1c6ad-53f8-4884-9147-0ac451c12e8d" />

# Back Side
<img width="1080" height="1500" alt="image" src="https://github.com/user-attachments/assets/03622e52-091c-410f-9213-f2d8e2a5aff6" />


# Overview:
The Telemetry (TEL) board serves as the central data hub for the solar car and interfaces betweenn all of the car's internal sensors and the pitcrew. This board serves as the final destination for all data on the car that requires over-the-air (OTA) transmission. This data includes:
- CAN Bus
- Accelerator and Brake Pedals
- Battery Management System
- Solar Array Temperature
- Motor Speed and Temperature
- etc...

The TEL utilizes two different mediums for transmitting data OTA:
- **Radio** for close-proximity communication directly between the solar car and receiving team. Will primarily be used for close proximity communication during the American Solar Challenge (ASC).
- **Cellular** for long-range communication utilizing cell towers for extended coverage between the car and the track-side pit crew. Will primarily be used on the track for the Formula Sun Grand Prix (FSGP) where radio does not offer full range of coverage.

# Design Choices
The telemetry board utilizes the STM32F103RCT6 microcontroller for on-board data processing and interfacing between the board's many peripherals. This board handles both cellular and radio communication, supplies 3.3V and 12V to external sensors and peripherals, and extends CAN network for the car's memorator used for data logging. 

- Supports up to 10 external sensors via ADC channels through molex minifit connectors.
- Interfaces with the GPS and IMU using I2C communication, allowing for fast and reliable data transfer
- Utilizes the 900MHz XBee-PRO SX radio module for reliable radio communication
- Interfaces with a Raspberry Pi and NETGEAR hotspot using UART for reliable cellular communcation
- Incorporates a reliable asymmetric mounting system for UBC Solar designed and PCBWay-sponsored IMU and GPS breakout boards
<img width="216" height="288" alt="image" src="https://github.com/user-attachments/assets/9d7a762e-2142-49de-88d0-585e363c7ac4" />


- Used a 4-layer pcb stackup to minimize EMI and crosstalk between sensitive communication lines and signals

# Design Goals & Requirements
The Telemetry Rev3.0 was designed with the idea of robustness and future proofing in mind, allowing for further improvements without needing a full redesign. This board considers:
- EMI:
- Power Delivery:
