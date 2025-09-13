# automatic_hand_sanitizer_machine
IOT Projrct, C++, Arduino
Here’s a **README description** you can put in your project folder:

---

# Arduino Water Pump Control System

## Overview

This project uses an **Arduino UNO**, an **HC-SR04 ultrasonic sensor**, and a **relay module** to automatically control a **water pump**. The system monitors the water level in a tank and turns the pump **ON** when the water is low and **OFF** when the tank is full.

## Components Used

* Arduino UNO
* HC-SR04 Ultrasonic Distance Sensor
* Relay Module (to switch pump)
* DC Water Pump
* Power Supply / Battery

## Working Principle

1. The **ultrasonic sensor** measures the distance between the sensor and the water surface.
2. If the distance is **greater than a threshold** (tank level is low), the Arduino turns the **pump ON** through the relay.
3. If the distance is **less than another threshold** (tank is full), the pump is turned **OFF**.
4. The system runs continuously and updates the water level every second.

## Pin Connections

* **Ultrasonic Sensor**

  * VCC → 5V (Arduino)
  * GND → GND (Arduino)
  * TRIG → Digital Pin 2 (Arduino)
  * ECHO → Digital Pin 3 (Arduino)

* **Relay Module (Pump Control)**

  * Signal → Digital Pin 8 (Arduino)
  * VCC → 5V
  * GND → GND
  * Relay output → Pump (connected to external battery)

## Arduino Code

* Reads distance from HC-SR04 sensor
* Turns pump **ON** if distance > 15 cm (low water)
* Turns pump **OFF** if distance < 5 cm (full tank)
* Uses `pulseIn()` to measure ultrasonic echo time

## Customization

* Adjust `lowLevel` and `highLevel` values in the code according to your tank depth.
* Add hysteresis (safety margin) to avoid rapid switching of the pump.
* Can be extended with an LCD or IoT module to display water levels remotely.

