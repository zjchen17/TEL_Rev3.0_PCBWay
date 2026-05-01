# UBC Solar x [**PCBWay**](https://www.pcbway.com/) Sponsorship for Telemetry Board V3 Showcase!
> Below are all the PCBs UBC Solar has sponsored with [**PCBWay**](https://www.pcbway.com/). 
> * ⭐ [**PCBWay**](https://www.pcbway.com/) provides reliable PCB manufacturing and assembly services, offering a wide range of cost-effective options for rapid prototyping and small-volume production. 
> * 🌟 [**PCBWay**](https://www.pcbway.com/) kindly supported all these project with manufacturing and design review! Please visit their site if you need PCB manufacturing or assembly services. 
> * ⭐ There are lots of options for low-cost prototyping and small series production. 
> * 🌟 Their 24/7 support for payments and for reviewing makes our teams production scale rapdiy!

# Author: Jacky Chen (Power and Signals)

# Acknowledgement
A huge thank you to [PCBWay](https://www.pcbway.com/) for supporting this project by manufacturing our Telemetry V3 boards. Their reliable PCB fabrication and assembly services provide exactly what student design teams need: cost-effective, high-quality options for rapid prototyping and low-volume production.

# 2D Layout View
<img width="1218" height="1193" alt="image" src="https://github.com/user-attachments/assets/dd2cdb1d-b26c-4469-91ee-f7123680f373" />
_This image showcases the 2D Altium layout_

# Front Side
<img width="1080" height="1500" alt="image" src="https://github.com/user-attachments/assets/39d1c6ad-53f8-4884-9147-0ac451c12e8d" />
_This image highlights the frontside of the pcb which contains all the soldered-on components_

# Back Side
<img width="1080" height="1500" alt="image" src="https://github.com/user-attachments/assets/03622e52-091c-410f-9213-f2d8e2a5aff6" />
_This image highlights the backside of the pcb_

# Overview:
The Telemetry (TEL) board serves as the central data hub for the solar car and interfaces betweenn all of the car's internal sensors and the pitcrew. This board serves as the final destination for all data on the car that requires over-the-air (OTA) transmission. This data includes:
- CAN Bus
- Accelerator and Brake Pedals
- Battery Management System
- Solar Array Temperature
- Motor Speed and Temperature
- and more!...

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
<img width="1505" height="1189" alt="image" src="https://github.com/user-attachments/assets/ae6e4ba9-46a5-4fba-aac2-b172df2b809a" />
_This image showcases the 3D render of the pcb with all components and 3D bodies_

# Design Goals & Requirements
The Telemetry Rev3.0 was designed with the idea of robustness and future proofing in mind, allowing for further improvements without needing a full redesign. This board considers:
- Reliable Data Transmission: Ensures all necessary data from the car gets to where it needs to be without any interuptions.
- EMI Protection: 4-layer pcb stackup to ensure stable GND referencing and stitching vias between pours. Ensured eaech signal has dedicated return-current vias for proper grounding in fast switching signals.
- Power Or-ing: Utilize the LM66200 idead diode for power or-ing between two input sources ensuring proper functionality and safety in operating the TEL

# Future Improvements
The TEL can be further improved by adding labling to the different pins on the GPS and IMU mounting headers which allows for easier debugging inthe future. Additionally, board area can be optimized to allow for more peripherals without increasing size. The GPS and Radio can be moved further apart to help reduce signal interference due to the large power difference in their antennas. The IMU can also be placed closer to the center of the board for better stability and more accurate readings.
