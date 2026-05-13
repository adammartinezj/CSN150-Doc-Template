# Cybersecurity : CSN150  
## Project: ESP32-CAM Access Point Web Server

## Purpose
The purpose of this project was to set up the ESP32-CAM as a Soft Access Point web server using Arduino IDE. This lets devices like phones and computers connect directly to the ESP32-CAM without using a router. The ESP32-CAM creates its own Wi-Fi network and hosts a live camera stream.

---

## Equipment
* ESP32-CAM Module

* USB Micro Data Cable

* FTDI Programmer / ESP32-CAM-MB

* Arduino IDE

---

## Links to Documentation and Tools

##### GitHub Repository Template
https://github.com/ereedsanchez/CSN150-Doc-Template

##### ESP32-CAM Access Point Tutorial
https://randomnerdtutorials.com/esp32-cam-access-point-ap-web-server/

##### Arduino IDE
https://www.arduino.cc/en/software

##### ESP32 Board Package
https://raw.githubusercontent.com/espressif/arduino-esp32/gh-pages/package_esp32_index.json

##### AI GPTs Used
* ChatGPT

---

## Access Point vs Station

Normally the ESP32-CAM connects to a router like a normal Wi-Fi device. In this project the ESP32-CAM was changed into a Soft Access Point. This means it creates its own Wi-Fi network that devices can connect to directly.

Instead of using a router, devices connect straight to the ESP32-CAM network and open the web server with this IP:

```cpp
192.168.4.1
```

---

## Steps I Followed

1. Installed Arduino IDE.

2. Added the ESP32 Board Manager URL in:
File > Preferences > Additional Boards Manager URLs

3. Installed the ESP32 board package.

4. Connected the ESP32-CAM using a USB micro data cable and FTDI programmer.

5. Opened:
File > Examples > ESP32 > Camera > CameraWebServer

6. Changed the camera model to AI Thinker:

```cpp
#define CAMERA_MODEL_AI_THINKER
#include "camera_pins.h"
```

7. Changed the project from station mode to access point mode.

8. Added the Wi-Fi name and password:

```cpp
const char *ssid = "ESP32-CAM Access Point";
const char *password = "123456789";
```

9. Removed the normal Wi-Fi connection code:

```cpp
WiFi.begin(ssid, password);

while (WiFi.status() != WL_CONNECTED) {
  delay(500);
  Serial.print(".");
}
```

10. Added the access point code:

```cpp
WiFi.softAP(ssid, password);
```

11. Selected:
Tools > Board > AI Thinker ESP32-CAM

12. Selected the right COM port.

13. Uploaded the sketch.

14. Disconnected IO0 from GND after upload.

15. Pressed the RESET button.

16. Opened Serial Monitor at 115200 baud.

17. Saw this in Serial Monitor:

```cpp
WiFi Access Point Started
AP IP address: 192.168.4.1
```

18. Connected my phone and computer to the ESP32-CAM Wi-Fi network.

19. Opened a browser and typed:

```cpp
http://192.168.4.1
```

20. The live camera stream loaded successfully.

---

## Problems and Solutions

### Problem 1
**Problem:** Arduino code would not upload to the ESP32-CAM.

**Solution:**  
I had to hold the IO0/BOOT button while uploading. After it finished uploading, I disconnected IO0 from GND and pressed RESET.

---

### Problem 2
**Problem:**  
Camera init failed with error 0x105

**Solution:**  
The camera ribbon cable was loose. I unplugged it and connected it again correctly.

---

### Problem 3
**Problem:** COM port was not showing in Arduino IDE.

**Solution:**  
The USB cable I used only charged the board and did not transfer data. I switched to a USB data cable and it worked.

---

### Problem 4
**Problem:** ESP32-CAM stayed in download boot mode.

**Solution:**  
IO0 was still connected to GND after uploading. I disconnected it and pressed RESET again.

---

### Problem 5
**Problem:** Camera web page would not load.

**Solution:**  
I forgot to connect my device to the ESP32-CAM Wi-Fi network first. After connecting to it and opening 192.168.4.1 the camera stream worked.

---

## Screenshots to Submit

1. Arduino IDE successful upload  
2. Serial Monitor showing AP IP address  
3. ESP32-CAM Wi-Fi network  
4. Browser showing live stream  
5. GitHub documentation page  
6. ESP32-CAM setup  

---

## Final Report

In this project I set up the ESP32-CAM as a Soft Access Point web server using Arduino IDE. Instead of connecting to a router, the ESP32-CAM created its own Wi-Fi network called “ESP32-CAM Access Point”. Devices connected directly to the ESP32-CAM and opened the live camera stream using the IP address 192.168.4.1.

During this project I learned how to upload code to the ESP32-CAM, change it from station mode to access point mode, and troubleshoot common errors like upload problems, camera errors, and boot mode issues. I also learned more about how wireless access points work in IoT devices and networking.
