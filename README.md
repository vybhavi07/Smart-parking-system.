# Smart-parking-system.
The Smart Parking System uses Arduino and an ultrasonic sensor for collision alerts through LEDs and a buzzer. An ESP32 monitors four parking slots and hosts a Wi-Fi webpage displaying vacant and occupied spaces in real time, improving parking safety, convenience, and space management.
🚗 Smart Parking System

An Arduino- and ESP32-based smart parking solution that improves parking safety and simplifies parking space monitoring using ultrasonic sensors, LEDs, a buzzer, and a Wi-Fi webpage.

📌 Project Overview

The project consists of two independent subsystems:

1. 🚨 Safety Parking Alarm

- Uses an Arduino and an ultrasonic sensor to measure the distance between a vehicle and an obstacle.
- Green LED: Safe distance.
- Yellow LED: Caution zone.
- Red LED + Buzzer: Obstacle detected at a dangerously close distance.
- Helps reduce the risk of collisions while parking.

2. 🅿️ Real-Time Parking Slot Monitoring

- Uses an ESP32 and four ultrasonic sensors to monitor four parking slots.
- Hosts a local Wi-Fi webpage displaying live slot availability.
- Displays each slot as VACANT, OCCUPIED, or SENSOR ERROR.
- Shows the total number of available and occupied slots.
- Automatically refreshes the webpage every two seconds.

✨ Features

- Real-time parking slot monitoring
- Distance-based parking safety alerts
- LED indicators and audible warnings
- Four-slot availability tracking
- Wireless monitoring through a local webpage
- Low-cost, beginner-friendly hardware
- No internet connection required for the local webpage

🧰 Hardware Requirements

- Arduino Uno or compatible board
- ESP32 development board
- 5 × HC-SR04 ultrasonic sensors (1 for the safety alarm and 4 for slot monitoring)
- LEDs: Green, Yellow, and Red
- 3 × current-limiting resistors for the LEDs
- 1 × active buzzer
- 4 × 1 kΩ resistors
- 4 × 2 kΩ resistors for ESP32 echo voltage dividers
- Breadboard and jumper wires
- USB cables and suitable power supplies

🔌 Pin Connections

Arduino — Safety Alarm

Component| Arduino Pin
Ultrasonic TRIG| D9
Ultrasonic ECHO| D10
Green LED| D4
Yellow LED| D5
Red LED| D6
Active Buzzer| D7

Connect each LED through a suitable current-limiting resistor.

ESP32 — Parking Slot Monitoring

Parking Slot| TRIG Pin| ECHO Pin
Slot 1| GPIO 13| GPIO 34
Slot 2| GPIO 14| GPIO 35
Slot 3| GPIO 25| GPIO 32
Slot 4| GPIO 26| GPIO 33

Important: HC-SR04 ECHO outputs can be 5 V, while ESP32 GPIO inputs are not 5 V tolerant. Use a voltage divider on every ECHO line before connecting it to the ESP32. Connect all grounds together.

For each voltage divider, connect a 1 kΩ resistor between ECHO and the ESP32 input junction, and a 2 kΩ resistor between that junction and GND.

💻 Software Requirements

- Arduino IDE
- Arduino board support package
- ESP32 board support package
- A web browser on a phone or computer

The ESP32 firmware uses the standard "WiFi.h" and "WebServer.h" libraries included with the ESP32 Arduino core.

🚀 Getting Started

Step 1: Upload the Arduino Code

1. Connect the Arduino to your computer.
2. Open the safety alarm sketch in Arduino IDE.
3. Select the correct board and COM port.
4. Upload the code.

Step 2: Upload the ESP32 Code

1. Connect the ESP32 to your computer.
2. Open the parking slot monitoring sketch.
3. Select the correct ESP32 board and COM port.
4. Upload the code.

Step 3: Open the Parking Dashboard

1. Power on the ESP32.

2. Connect your phone or computer to the Wi-Fi network:
   
   - SSID: "SmartParking4"
   - Password: "Park1234"

3. Open a browser and visit:
   
   "http://192.168.4.1"

4. View the real-time status of all four parking slots.

⚙️ Working Principle

The ultrasonic sensors measure the distance to nearby objects. The Arduino uses distance thresholds to control the safety LEDs and buzzer. The ESP32 independently checks the four parking slots and updates a locally hosted webpage with their availability.

Default thresholds can be adjusted in the source code according to the dimensions of the parking model and sensor placement.

📷 Project Demonstration



Example:

- "images/circuit_diagram.png"
- "images/hardware_setup.jpg"
- "images/dashboard.png"

🔮 Future Improvements

- Connect the safety alarm to the ESP32 dashboard.
- Add cloud-based monitoring and remote access.
- Develop a mobile application.
- Add automatic parking reservations.
- Integrate entry and exit counting.
- Add payment and time-based booking features.

🎯 Applications

- Shopping malls
- Colleges and universities
- Office buildings
- Residential parking areas
- Small commercial parking facilities

👥 Project Information

Project: Smart Parking System with Safety Alarm and Real-Time Slot Monitoring
Domain: Embedded Systems, IoT, and Smart Transportation
Platforms: Arduino and ESP32

📄 License

This project is intended for educational and demonstration purposes. Add a suitable open-source license, such as the MIT License, if you want others to reuse and modify your code.

---

⭐ If you find this project useful, consider starring the repository!
