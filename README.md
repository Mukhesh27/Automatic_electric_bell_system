🎯 Objectives Automate bell ringing at fixed times without manual intervention.

Provide manual override and remote control features.

Customize bell tones and durations.

Incorporate sensors for safety and smart automation.

Build a user-friendly system using affordable components.

🛠️ Hardware Components Component Description Arduino Uno / Nano Main microcontroller Real-Time Clock (RTC DS3231) Keeps accurate time for scheduling Relay Module Controls the electric bell circuit Buzzer/Speaker Produces bell sound LCD Display (16x2) Shows time and system status Keypad or Push Buttons Used for manual input and override WiFi Module (ESP8266) Enables remote control via IoT IR / PIR Sensor (optional) Detects motion for smart features MicroSD Module (optional) Stores schedule data Power Supply Powers the system (via adapter or USB) Breadboard & Jump Wires For circuit connections Transistor + Diode For relay protection

⚙️ Software and Tools Arduino IDE – Code development and flashing

Embedded C / Arduino C++

Optional: Blynk App / Firebase – For IoT control

Fritzing / Tinkercad – Circuit simulation (optional)

GitHub – Version control and collaboration

🧠 Features ✅ Automatic Bell Scheduling

✅ Real-Time Clock (RTC) Accuracy

✅ Manual Override Button

✅ Remote Control via App/Web

✅ Customizable Bell Sound

✅ LCD Display with Clock and Status

✅ Motion-Activated Bell (optional)

✅ Power-Loss Recovery Support

✅ Expandable and Modular Design

🔌 How It Works The RTC module provides real-time tracking.

The Arduino compares current time with predefined schedules.

When the scheduled time matches, the relay is triggered.

The relay activates the bell for a specific duration.

Optional LCD shows time and bell status.

Manual buttons or remote app can override or trigger the bell.

🔁 Bell Modes Auto Mode: Rings at programmed times.

Manual Mode: Triggered by button/app.

Sensor Mode: Rings when motion is detected (e.g., during fire drills).

Silent Mode: Temporarily disables all ringing (e.g., during exams).

🧾 Sample Schedule Format (EEPROM/SD/Firebase) json Copy Edit [ {"time": "08:00", "duration": 5}, {"time": "10:00", "duration": 3}, {"time": "12:30", "duration": 5}, {"time": "15:00", "duration": 4} ] 🖥️ Circuit Diagram ⚠️ A Fritzing or Tinkercad diagram can be added here.

Connect the RTC SDA & SCL to A4 & A5 (for Uno).

Relay IN to digital pin (e.g., D7).

Buzzer/Relay output connects to AC/DC bell.

LCD uses I2C (A4 - SDA, A5 - SCL).

Push buttons on digital pins with pull-down resistors.

🧑‍💻 Arduino Code Overview setup(): Initializes modules, RTC, LCD, pins.

loop(): Constantly checks the time and triggers bells.

triggerBell(): Activates bell and handles duration.

manualControl(): Checks if a button or app has triggered manual mode.

loadSchedule(): Retrieves schedule from EEPROM or Firebase.

📲 IoT/Remote Control (Optional) ESP8266 or ESP32: Connect to WiFi

Blynk/Firebase/MQTT: Remote command delivery

Mobile App: Toggle bell, set schedules, view logs

🧪 Testing Instructions Upload the code using Arduino IDE.

Ensure RTC is set correctly.

Use Serial Monitor for logs.

Test automatic and manual modes.

Simulate motion or time triggers.

🧰 Troubleshooting Issue Solution Bell not ringing Check relay connections and pin code Wrong time displayed Reset RTC using Arduino sketch Manual button not working Verify pull-down resistor & pin state WiFi not connecting (IoT) Check credentials and network range

🚀 Future Enhancements Add web dashboard to edit schedules

Battery backup with RTC module

Dual bell outputs for different tones

Voice alerts or MP3 sound playback

Log ringing history to SD or Firebase

App notifications for missed rings
