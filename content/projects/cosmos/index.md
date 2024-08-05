---
title: "UCD COSMOS"
date: 2024-08-16
draft: false
summary: "Building a smart white cane"
---

## BeepBeep

For our [COSMOS](https://cosmos-ucop.ucdavis.edu/app/main) 2024 Cluster 8 (Internet of Things) final project, Jessie Luo and I prototyped BeepBeep, an IoT device that utilizes four different sensors to turn a white cane smart.

We programmed our device with the Arduino, although we spent most of the program learning with the Ti MSP432.

![cluster board](images/IMG_4228.png)

## Obstacle Detection

We used an ultrasonic sensor to detect obstacles within a certain range. As you get closer to the object the frequency of the buzzing increases. Turn the trigger pin high which sends an ultrasonic signal which is received by the sensor as an echo. The pulseIn() function returns how long the signal takes to return back to the sensor. The speed of sound travelling in air is approximately 0.0343 cm/microseconds so we can use that and the time to calculate how far away the obstacle is.

{{<youtube M4rvbWB7oIs>}}

## Fall Detection

Using the accelerometer, we implemented a feature that detects when the user has dropped the cane. Once dropped, the cane will start buzzing until picked back up again. By continuously measuring the net acceleration from x, y, and z, we can check if the net acceleration is 0 and in free fall.

{{<youtube Kbi75S_lzhw>}}

## Lightsaber

This was my favorite feature. The cane automatically turns on LEDS to helps other people or vehicles notice the user in dark areas. This was done with the Adafruit TSL2591 light sensor, constantly checking the light levels with our defined threshold.

{{<youtube b2QBTMVoh7E>}}
