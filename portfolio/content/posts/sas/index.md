+++
title = "Sensor Acquisition System"
date = "2021-09-11"
author = ""
authorTwitter = "" #do not include @
cover = ""
tags = ["", ""]
keywords = ["", ""]
description = ""
showFullContent = false
readingTime = false
hideComments = false
+++

# Introduction
## Requirements:
- Support up to 16 sensors simultaneous
- Support different kind of sensors, must be easily upgradable to support new ones
- Independent conditioning of the signal for each sensor (1 board per sensor)
- Transmit the data to the computer which will log it
- Settings must be set from the computer
- Sampling rate of 1kHz
- Resolution of 16bits
- Required supported sensors:
    - force sensor using Wheastone bridge
    - Thermocouple
    - Pressure sensor

# Project Architecture
{{< image src="architecture.PNG" >}}

# Components
The list of components used has changed quite a lot thorough the design, I will for the sake of clarity only talk about the final design choice.

## Analog to Digital Converter
Accordingly to the requirements, the ADC must have 16 physical pins to which the sensors would be always connected.
Moreover it has to sample each 16 sensors at a resolution of 16 bits at 1kHz.

## MCU
The MCU must validates the following requirements:
- 2 SPI interface of at least 256 kbits/s (one for the ADC, the other for the USB port)
- be of the STM32 family (since it's the one mostly used at the ERT)
- handle a SPI data traffic of 256 kbits/s from the ADC

In order to reduce the workload on the PCB design, the MCU must be already assembled on a board featuring :
- USB interface for transmitting data/debugging/programming of the MCU
- Header pins such that it can plugged as a shield on the main PCB board

The chosen MCU is the Nucleo STM32 F446RE.

## Power Supply
Many voltages are needed : 5V, 3.3V, 9V, 12V.

# Hostboard A
{{< image src="Hostboard_A_schema.PNG" >}}
{{< image src="Hostboard_A_pcb3D_1.PNG" >}}
{{< image src="Hostboard_A_pcb3D_2.PNG" >}}
PCBs assembly
{{< image src="hostboard_raw.JPG" >}}
Assembled PCBs with test pcb
{{< image src="hostboard_assembled.JPG" >}}

# Daugtherboard
{{< image src="Daughterboard_schema.PNG" >}}
{{< image src="Daughterboard_pcb3D_1.PNG" >}}
{{< image src="Daughterboard_pcb3D_2.PNG" >}}

# PCBs assembly
{{< image src="PCBs_assembly.PNG" >}}
