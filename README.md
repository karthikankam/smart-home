# 🏠 Smart Home Automation Project (Arduino-Based)

This project is an **Arduino-based Smart Home System** designed to automate home appliances using a serial interface. It includes control over lights, a servo motor (possibly for door lock mechanism), and sound alerts. The system reacts to specific commands sent via the Serial Monitor or another serial device (like a Bluetooth module or mobile app).

## 🔌 Hardware Requirements

- Arduino Uno or compatible board  
- Servo Motor  
- Buzzer or Speaker (connected to pin 6)  
- LEDs (or connected relays for home appliances)  
- Push Button / Sensor on pin 12 (used as a trigger)  
- Wires and breadboard  
- Power supply or USB

## 🧠 Features

- Control lights, buzzers, and a servo motor via serial commands.
- Reacts to button or sensor input.
- Provides feedback over serial monitor.
- Simulates basic automation routines using pre-programmed sequences.

## 🧾 Serial Commands

| Command | Description |
|---------|-------------|
| `3`     | Waits for button input. If detected, triggers a light dimming and blinking pattern. |
| `A`     | Turns off all devices first, then blinks three LEDs in sequence, vibrates (buzzer), and moves the servo to 120° (e.g., unlock door). |
| `B`     | Resets all outputs to LOW and moves the servo to 0° (e.g., lock door). |
| `1`     | Turns on the main light (pin 13). |
| `0`     | Turns off the light and buzzer. |
| Others  | Triggers a default beep sound for 1 second. |

## 🧪 How to Use

1. **Upload the code** to your Arduino board using the Arduino IDE.
2. Open **Serial Monitor** (set baud rate to `9600`).
3. Type commands like `A`, `B`, `1`, or `3` to interact with the system.
4. Watch how the connected devices (LEDs, servo, buzzer) respond.

## 🔧 Pin Configuration

| Pin | Component         |
|-----|-------------------|
| 13  | Light (LED/Relay) |
| 6   | Buzzer / PWM output |
| 12  | Button / Sensor input |
| 11, 10, 3 | LEDs (Sequence indicators) |
| 2   | Extra Output LED |
| 4   | Servo Motor |

## 🛠 Libraries Used

- [Servo.h](https://www.arduino.cc/en/reference/servo)

Make sure to include the Servo library before uploading:
```cpp
#include <Servo.h>
