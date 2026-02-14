# 📧 How to Send Email Using ESP32

## 🚀 ESP32 Email Alert System Using Ultrasonic Sensor

This project demonstrates how to send alert email using ESP32 when a specific condition is triggered. The ESP32 is interfaced with an ultrasonic sensor, and when the measured distance falls below a predefined threshold, the board automatically sends an email notification using the CircuitDigest Cloud Email Notification API.

This project is ideal for learning IoT-based real-time alert systems using secure HTTPS communication.

---

## 🧠 Project Overview

The ESP32 continuously monitors distance using an ultrasonic sensor.  
If the measured distance becomes less than 30 cm:

- The system detects it as a trigger event
- ESP32 connects to WiFi
- Sends structured JSON data to Cloud Email API
- Registered email receives alert notification

This creates a real-time ESP32 email notification system.

---

## 🛠️ Components Required

| S.No | Component | Purpose |
|------|------------|----------|
| 1 | ESP32 | Main controller |
| 2 | Ultrasonic Sensor (HC-SR04) | Distance measurement |
| 3 | Breadboard | Easy connections |
| 4 | Jumper Wires | Circuit wiring |

---

## 🔌 Circuit Connections

| Ultrasonic Sensor Pin | ESP32 GPIO |
|-----------------------|------------|
| VCC | 5V / 3.3V |
| GND | GND |
| TRIG | GPIO 32 |
| ECHO | GPIO 33 |

---

## ⚙️ Working Principle

1. ESP32 initializes WiFi and ultrasonic sensor.
2. Sensor sends ultrasonic pulse.
3. Echo signal is measured to calculate distance.
4. If distance < 30 cm:
   - ESP32 triggers email notification.
5. Boolean flag prevents repeated emails.
6. When object moves away, system resets.

---

## 🌐 ESP32 Email Notification Process

- Connects to WiFi
- Creates secure HTTPS client
- Prepares JSON payload
- Sends request to Cloud Email API
- Cloud processes request
- Email is delivered instantly

---

## 🔐 Key Features

✔ Real-time distance monitoring  
✔ Secure HTTPS communication  
✔ Structured JSON email request  
✔ Event-based alert triggering  
✔ Prevents repeated notifications  
✔ Easy cloud integration  

---

## 📄 Important Code Sections

### Include Required Libraries
```cpp
#include <WiFi.h>
#include <WiFiClientSecure.h>
```

### Define Pins
```cpp
#define TRIG_PIN 32
#define ECHO_PIN 33
```

### Email Trigger Logic
```cpp
if (dist > 0 && dist < 30 && !emailSent) {
  sendEmail(dist);
  emailSent = true;
}
```

---

## 📬 Example Use Cases

- Intrusion Detection System  
- Proximity Alert System  
- Smart Parking Sensor  
- Safety Monitoring  
- Industrial Automation Alerts  

---

## 🔧 Troubleshooting

### WiFi Not Connecting
- Check SSID and password.
- Ensure 2.4GHz network.
- Verify signal strength.

### Email Not Received
- Verify API key.
- Confirm registered email.
- Check HTTPS port (443).

### Repeated Emails
- Ensure emailSent flag is implemented properly.

---

## 🔮 Future Enhancements

- Add multiple sensors
- Add image-based alert
- Store data in cloud database
- Add SMS or mobile app notifications
- Dashboard visualization

---

## 📚 Learning Outcome

After completing this project, you will understand:

- ESP32 WiFi communication
- Secure HTTPS client usage
- JSON payload formatting
- Cloud API integration
- Event-based IoT notifications

---

## 📌 Conclusion

This project demonstrates how to build a reliable ESP32 email alert system using an ultrasonic sensor and cloud-based Email Notification API. It shows how IoT devices can automatically send real-time alerts without manual supervision.

The system is scalable, secure, and suitable for real-world automation applications.

---

## 👨‍💻 Author

Vedhathiri. K

