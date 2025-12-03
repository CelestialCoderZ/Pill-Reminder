# ⚕️ Smart Pill Reminder with ESP32

A compact medication reminder system built using an ESP32, DS3231 RTC, buzzer, LED indicators, pushbutton, and servo motor.
The device notifies users at predefined times using sound and light cues and lets them confirm dose intake through a button press.

## 🎯 Overview
This system is designed to help users take their medicine on schedule. At the exact set time, the ESP32 activates alerts and opens the servo-based pill compartment. When the user presses the confirmation button, the reminder stops, the green LED lights up, and the tray closes. If no response is detected within a short timeout, the system marks it as a missed dose.

## 🚀 Features

- Precise timekeeping using RTC DS3231
- Audible and visual alerts at medicine time
- Red LED signals an active reminder
- Green LED shows the dose was taken
- Pushbutton to acknowledge medication
- Servo motor mimics a pill dispenser tray
- Fully customizable schedule
- Missed-dose detection

## 🛠️ Hardware Components

| Component | Description |
|-----------|---------------|
| ESP32 | Microcontroller |
| RTC DS3231 | Real-time clock module |
| BUZZER | Audio alert for pill time |
| RED LED | Indicates pill due |
| GREEN LED | Confirms pill taken |
| PUSH BUTTON | For user confirmation |
| SERVO MOTOR | Simulated pill sidpenser door |
| JUMPER WIRES & BREADBOARD | For connections |

## 🧠 How It Works
    1) The ESP32 reads the current time from the DS3231 clock module.
    2) When the time matches a scheduled dose:
            - The buzzer activates
            - The red LED turns on
            - The servo rotates to open the tray
    3) Once the user presses the button:
            - Alerts stop
            - Green LED turns on briefly
            - The servo closes the tray
    4) If there is no interaction, the system classifies it as a missed dose.
## 🔌 Circuit Connection


| COMPONENTS | ARDUINO UNO | CONNECTION TYPE | DESCRIPTION |
|-----------|---------------|---------------|---------------|
| RED LED | GPIO26 | OUTPUT | Turns ON when it's pill time |
| GREEN LED | GPIO27 | OUTPUT | Indicates medicine taken |
| PUSHBUTTON | GPIO14 | INPUT_PULLUP | Press to confirm pill taken |
| BUZZER | GPIO25 | OUTPUT | Sounds alarm at pill time |
| SERVO MOTOR (SIGNAL PIN) | GPIO17 | PWM OUTPUT | Opens/closes pill tray |
| RTC DS3231-SDA | GPIO21 | I²C DATA LINE | Communicates time data |
| RTC DS3231-SCL | GPIO22 | I²C CLOCK LINE | Synchronizes RTC timing |
| RTC DS3231-VCC | 3.3V | POWER | Powers the RTC module |
| RTC DS3231-GND | GND | GROUND | Common ground connection |

## 💻 Code Overview
                   int pillHours[]   = {9, 13, 22};
                   int pillMinutes[] = {0, 0, 30};
    These arrays define the pill reminder times (9:00 AM, 1:00 PM, and 10:30 PM).
    Modify them as per your medicine schedule.
  
    **Key Functions**-

      - triggerReminder() → Activates buzzer, LED, and servo
      - stopReminder() → Stops alert and confirms intake
      - missedDoseAlert() → Handles unacknowledged reminders

## ⚡ Quick Start
    1. Clone the repository:
       git clone https://github.com/yourusername/Smart-Pill-Reminder-Dispenser-Using-ESP32.git
       cd Smart-Pill-Reminder-Dispenser-Using-ESP32

    2. Instruction:
      - Install Arduino IDE (v2 or newer)
      - Add ESP32 board support via Boards Manager
      - Install required libraries:
                  (i)  RTClib
                  (ii) ESP32Servo
    3. Connect the components as per the table above
    4. Upload the code to your ESP32
    5. Open Serial Monitor at 115200 baud to view logs
      
## 🚀 Future Enhancements
   - Add LCD/OLED display for real-time clock and next dose info.
   - Integrate Wi-Fi & mobile alerts for missed doses.
   - Store schedules in EEPROM/NVS for persistence
   - Add a configuration menu via web or app interface
   

## 🤝 Contributing

Contributions are welcome! Here are ways you can help:

### 🐛 Reporting Bugs
- Open an issue with detailed description
- Include steps to reproduce
- Add relevant code/screenshots

### 💡 Suggesting Enhancements
- Describe the new feature
- Explain the use case
- Consider implementation approach

### 🔧 Code Contributions
    1. Fork the repository
    2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
    3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
    4. Push to the branch (`git push origin feature/AmazingFeature`)
    5. Open a Pull Request

## 🙏 Acknowledgments
     
- Arduino Community for continuous support
- Open-source hardware and software contributors


## 📞 Contact Me
If you have any questions, suggestions, or feedback, feel free to reach out:

 - **Name**: ANUPRABHA BAG
 - **Email**: [anuprabhabag2004ind@gmail.com]
 - **LinkedIn**: [linkedin.com/in/yourprofile](https://www.linkedin.com/in/anuprabha-bag-b98359260/)
 - **GitHub**: [github.com/yourusername](https://github.com/CelestialCoderZ)
   
💡 I’d love to connect and collaborate on exciting projects!



