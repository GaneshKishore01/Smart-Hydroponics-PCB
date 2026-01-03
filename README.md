<img width="1920" height="1080" alt="image" src="https://github.com/GaneshKishore01/Smart-Hydroponics-PCB/blob/main/src/centre.png" /># MSM-T
A Software designed for tracking torrents and monitoring peers conneted to it.
# **Description**

## **What it is**
A ready-to-use printed circuit board capable of measuring pH, TDS, temprature & humidity.
The PCB also includes additional features/slots for:
- s3231 i2c rtc clock module for keeping Real world time
- Capable of switching 16 hours light and 8 hours darkness 
- Oled I2C with 4 buttons

## **How it works**
- **Power supply:**  
  It is powered by **12V barrel jack**, which breakes into smaller 5V to power arduino and sensors via a LM2596 buck.
The 12 V source is used to power the titillating/irrigation pump, whereas the 5V powers the dosing pump and draing pump.

- **Magnet search:**  
  Uses **Jackett** to aggregate torrent search results from multiple indexers.

---

## **Instructions**
1. Download `MSMT.zip` from releases.
2. **Extract** the contents of `MSMT.zip`
3. **Copy** the `MTSM` folder from `/assets` into:  
   `C:\Users\GANESH\AppData\Roaming\`
4. **Configure** the Jackett and qBittorrent ports in the **Settings** tab
5. Enjoy!

---
Automatic Dosing, Draining & Pumping System for High-Efficiency Hydroponics
Overview

This project is a microcontroller-based hydroponic control system designed to automate nutrient dosing, water circulation, and draining with high reliability and safety.
The system uses real-time sensor feedback (TDS, water level, temperature, humidity) and a button-driven OLED user interface, enabling both automatic and manual operation modes.

The design prioritizes:

Electrical safety and power separation
Accidental-operation prevention (software interlocks)
Expandability and modularity
Low-cost, widely available components
System Architecture
Control & Timing

Microcontroller: Arduino Uno Rev 3
Real-Time Clock: DS3231 (I²C)
Battery-backed
Used for time-based logic, scheduling, and stability across power loss

Power Architecture
Main Supply
AC-DC Power Brick:
Output: 12 V DC, 5 A (60 W)
Connector: 5.5 mm / 2.1 mm barrel jack
Female barrel jack adapter distributes the 12 V rail

Voltage Domains
Voltage Rail	Powered Devices
12 V DC	Plant growth LED, main water pump
5 V DC	Arduino Uno, sensors, OLED, peristaltic pumps
Step-Down Conversion

Buck Converter: LM2596S
Steps 12 V → 5 V
Powers logic, sensors, and peristaltic pumps
Common ground shared across all voltage domains

Actuators & Drivers
MOSFET Switching
MOSFET Model: IRLZ44N (logic-level N-channel)

Used to control:
12 V LED grow light
12 V water circulation pump
5 V nutrient dosing peristaltic pump
5 V drain peristaltic pump

MOSFETs allow:
High-current load control
Electrical isolation between Arduino and motors
PWM capability for future extensions
Pumps
Water Circulation Pump
Model: JT-500
Rating: 12 V DC, 600 L/h
Protection: IP68
Peristaltic Pumps
Model: ABC RC 12527
Voltage: 5 V DC
Functions:
Nutrient dosing
System draining

Sensors
Sensor	Function
TDS Meter V1.0	Measures nutrient concentration for automatic dosing
Water Level Sensor	Prevents dry-run and unsafe pump operation
DHT22	Ambient temperature & humidity monitoring
Dosing Logic
Fully TDS-based
System compares measured TDS against a target value
Nutrient pump activates automatically when TDS drops below threshold
Includes hysteresis to prevent rapid switching

User Interface
Display
OLED: 0.96" SSD1306 (I²C)

Displays:
Sensor data
System mode
Status messages
About / creator information

Buttons

Four tactile buttons provide full system interaction:

Button	Function
K1	Toggle between Automatic and Manual dosing modes
K2	Refresh display / exit idle screen
K3	Drain activation input (sequence-protected)
K4	About / creator information
Idle & UI Logic

After 15 seconds of inactivity, the system enters idle mode
An animated cat sequence plays on the OLED for 5 seconds
Any button press:
Immediately exits idle mode
Restores active system screen

Safety Mechanisms
Drain Protection (Software Interlock)
To prevent accidental draining, the drain pump is activated only if the following button sequence is entered correctly:
K3 → K3 → K1 → K2
This sequence-based confirmation significantly reduces unintended water loss.

Operating Modes
Automatic Mode
Nutrient dosing is controlled by:
Real-time TDS measurements
Predefined target values
Hysteresis for stability
Minimal user intervention required

Manual Mode
User manually controls dosing
Intended for:
Calibration
Maintenance
Testing and diagnostics

Design Goals
Reliable nutrient control
Electrical safety with mixed voltage domains
Clear and responsive UI
