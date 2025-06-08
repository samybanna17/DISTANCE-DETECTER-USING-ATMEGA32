# 📏 Distance Detector Using ATmega32

A simple embedded system project to measure distance using an **HC-SR04 ultrasonic sensor** and display it on a **16x2 LCD** via I2C interface, controlled by an **ATmega32 microcontroller**.

---

## 🚀 Overview

This project demonstrates:
- Interfacing an HC-SR04 ultrasonic sensor with ATmega32.
- Using **external interrupt INT0** and **Timer1** for pulse-width measurement.
- Converting the time of flight to distance in centimeters.
- Displaying real-time distance data on an I2C LCD screen.

---

## 🎯 Objectives

- Understand ultrasonic distance measurement using HC-SR04.
- Learn external interrupt handling with INT0.
- Implement timer-based distance calculation.
- Interface and display data on an I2C 16x2 LCD.
- Write efficient embedded C (AVR-GCC) and Assembly code.

---

## 🔧 Hardware Used

| Component                  | Description                                      |
|---------------------------|--------------------------------------------------|
| ATmega32 Microcontroller  | Main controller                                  |
| HC-SR04 Sensor            | Ultrasonic distance measurement                  |
| 16x2 LCD + I2C Module     | Output display (PCF8574)                         |
| 16 MHz Crystal Oscillator | System clock                                     |
| 22pF Capacitors (2x)      | Crystal stabilization                            |
| 10kΩ Potentiometer        | LCD contrast adjustment                          |
| 10kΩ Resistor             | Pull-up resistor                                 |
| 5V DC Power Supply / LM7805 | Power source                                   |
| LED, Push Button (Optional) | Indicators / manual control                    |
| Breadboard & Jumper Wires | Circuit prototyping                              |

---

## 🔌 Pin Configuration

- **HC-SR04 Trigger**: PD0 (Pin 14)
- **HC-SR04 Echo**: PD2 (INT0, Pin 16)
- **LCD Data Lines**: PA0–PA7

---

## 🧠 Working Principle

1. The **HC-SR04 sensor** sends a 40 kHz ultrasonic pulse via its TRIG pin.
2. It receives the reflected echo via the ECHO pin.
3. The **ATmega32** uses external interrupt INT0 to capture the echo duration.
4. **Timer1** measures the pulse width.
5. Distance is calculated using the formula:
Distance (cm) = Pulse Width (µs) / 58
6. The result is displayed on the 16x2 LCD.

---

## 💻 Software

- **Language:** C (AVR-GCC) & Assembly
- **Platform:** Atmel Studio
- **Libraries:** MrLCDmega32 for LCD handling

### ▶️ Sample Code Snippet (C)
```c
PORTD |= 1<<PIND0;      // Trigger pulse
_delay_us(15);
PORTD &= ~(1<<PIND0);   // Stop trigger
count_a = pulse / 58;   // Convert time to distance
🧩 Interrupt Service Routine (INT0)
Starts Timer1 on rising edge.

Stops Timer1 on falling edge.

Stores pulse width for distance calculation.

📊 Results & Observations
Accurate real-time distance display.

Stable and responsive readings using INT0 and Timer1.

Efficient I2C-based LCD output for compact wiring.

✅ Conclusion
This project successfully integrates:

HC-SR04 ultrasonic sensor

External interrupts and timers

Real-time data display on LCD

It is suitable for applications like obstacle detection, robotics, and smart measurement systems.

📚 References
ATmega32 Datasheet – Microchip

HC-SR04 Datasheet

"The AVR Microcontroller and Embedded Systems" – Mazidi et al.

Circuit Digest, Electronics Hub tutorials

AVR Freaks Forums & GitHub examples

✍️ Authors
Samir Hiteshbhai Makwana 

📧 Contact: samirmakvana71@gmail.com# DISTANCE-DETECTER-USING-ATMEGA32
