# Smart Water Level Indicator & Filling Time Identifier using ESP8266

# Project Overview

This project is designed to monitor water levelsand calculate filling time automatically using an ESP8266 microcontroller. The system integrates water level sensors, a CD4026 counter IC, 74HC147 encoder, and CD4511 decoder to display readings on a 7-segment display. It also features relay and motor control for automated tank filling.

Through continuous sensing and control, the system provides real-time feedback on water levels and filling duration, helping users manage water efficiently.

---

# Key Features

*  Water Level Detection using sensor input to ESP8266
* 7-Segment Display Output for water level and filling time
* Relay-Based Motor Control via BC547 transistor
* Automatic Filling Time Calculation
* Continuous Monitoring Loop for accurate updates
* Optional Wi-Fi Connectivity for remote data access

---

# Hardware Components

* ESP8266 Microcontroller
* Water Level Sensor
* Flow Sensor (optional for accuracy)
* CD4026 Counter IC
* 74HC147 Encoder
* CD4511 Decoder
* 7-Segment Display
* BC547 Transistor
* Relay Module
* Motor / Water Pump
* Power Supply

---

# System Working

# 1. Initialization

The ESP8266 initializes by connecting to Wi-Fi, configuring pins, and setting up variables for sensor reading, motor control, and display handling.

# 2.Water Level Sensing

The water level sensor detects the current water level and sends signals to the ESP8266 for processing.

# 3. Counting Water Level Events

As the water level changes (increasing or decreasing), the ESP8266 counts events using the CD4026 counter IC, which keeps track of level increments.

# 4. Display on 7-Segment Display

The CD4026 output is encoded by 74HC147 and decoded by CD4511, driving the 7-segment display to show the water level count in real time.

# 5. Motor Control

When the water level falls below a threshold, the ESP8266 activates a relay through a BC547 transistor, switching the motor ON to fill the container.

# 6. Filling Time Calculation

When the motor starts, the ESP8266 records the start time. Once the tank reaches the desired level, it turns the motor OFF and calculates filling time as:

```
Filling Time = End Time - Start Time
```

# 7. Display Filling Time

The calculated filling time is displayed on the same 7-segment display, driven by the CD4511 decoder and transistor network.

# 8. Loop Operation

The system continuously monitors the tank, updates display readings, and controls the motor automatically for repeated operation.

# 9. Optional Wi-Fi Communication

You can extend this project by enabling Wi-Fi connectivity on the ESP8266 to send live water level and filling time data to a web dashboard or cloud server.

---

# Methodology / Flowchart

Step-by-Step Flow:

1. Initialize the ESP8266 and connect to Wi-Fi.
2. Set initial variables and configure pins.
3. Continuously monitor water level sensor readings.
4. If water level < threshold:

   * Increment counter
   * Update 7-segment display
5. If water level ≥ threshold:

   * If motor not running:

     * Start motor, record start time, set motor state = running
   * If motor running and desired level reached:

     * Stop motor, calculate filling time, display it, set motor state = not running
6. Repeat loop continuously for real-time monitoring.

---

# Future Enhancements

* IoT integration with real-time cloud dashboard
* Mobile app notification for water level updates
* Calibration for different tank sizes
* Integration with voice assistants for smart home control

---

# Developed Using

* Arduino IDE
* C/C++ Programming
* ESP8266 Libraries
* Electronics & Embedded Systems Design

