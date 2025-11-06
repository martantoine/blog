+++
title = "DuploBuster"
date = "2023-06-14"
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

# Competition Specifications
The goal of this competition is to create an autonomous robot able to gather Duplo toys and drop them in the collection zone of the 8x8 meters arena that features obstacles and different terrains as shown bellow.
{{< image src="Arena.png" width="700px">}}
The room have four different regions with different color LEDs in every corner. The robot have 10 minutes inside the room to collect as many Duplo as it can.

# How the robot collects Duplo
- A claw grips the toy and elevates it into it's compartment
- Once the Duplo has picked up enough toys it releases them at the dropping zone by opening it's door
- The front camera uses machine learning to recognize Duplos while a LIDAR scans the environment for obstacles
- A 360° top camera gives the position and angle while an A* algorithm deduces it's trajectory

# Object Detection
## Problem Introduction
The duplo are localized using deep learning. In fact the Duplo comes in big variety of colors and shapes, making feature detection algorithm impractical in this situation.

## Dataset
Pictures of Duplo in the arena were captured using the same camera (Raspberry Pi Camera V2.1) that would then eventually be used for the inference.

A total of **600** pictures were capture, after deleting the non usable one, **523** remained.

The dataset was labelled on the free to use online platform *Roboflow*.

## Policy Training
The framework used for target identification is **YoloV6** (**YOLOv6-N** to be exact), it is the lightest and fastest to run model among all others (works with \textbf{640x640} pixels pictures). The policy was trained on *Google Colab* and exported to the *ONNX* format for inference.

## Results
The raw inference performance are the following:
| True positive | False positive |
|---------------|----------------|
|     83%       |       0%       |

{{< image src="input.jpg" >}}
{{< image src="output.png" >}}

# Electronics
## Sensor list
- Ultrasonic Distance Sensor HCS04 x 2
- Microswitch Sensor x 4
- MPU-9150
- RPLIDAR A1M8 
- Raspberry Pi Camera V2.1
- Webcam Logitech C720 

## Actuator list
- Maxon EC 32 flat (15 W), 1:60 gearbox
- DC motor x 2
- Stepper motor
- Buzzer

Most of those sensors and actuators are interfaced through **I2C**, **SPI**, **PWM** and **Serial**.

A STM32F4 is used for interfacing with the sensors and actuators in realtime.

A Raspberry Pi 4 Model B is used for more resource intensive task (e.g. computer vision).

## Connections diagram
{{< image src="electronic.png" >}}

## Electronic assembly
{{< image src="result_elec.png" >}}
1. Maxon 24/2 controller
2. DC Driver 15x2 Lite
3. Raspberry Pi Camera V2.1
4. Raspberry Pi 4 Model B
5. Nucleo F446
6. Breadboard + IMU + AMIS-30543
7. Power Board

## Custom PCB
{{< image src="aci_pcb.jpeg" >}}
connects sensors and actuators with the MCU and Raspberry Pi.

# Some hardware details
## LIDAR
{{< image src="LIDAR.jpg" >}}

## The claw (grasps the Duplo) 
{{< image src="claws.jpeg" >}}

## Driving wheels 
The front wheels are 3D printed using TPU
{{< image src="front_wheel.png" width="700px" >}}
{{< image src="coupler.jpeg" width="700px" >}}