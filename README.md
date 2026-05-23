Cybersecurity : CSN150

Project: ESP32 Login Attempt Tracker

Purpose

The purpose of this project was to make a fake login page using the ESP32 web server to show how phishing attacks and fake login pages work. The ESP32 hosts a webpage where someone can type a username and password. The login information then shows up in the Serial Monitor. This project was only made for learning and cybersecurity education purposes.

Equipment

AI Thinker ESP32-CAM
USB Micro Data Cable
Computer with Arduino IDE
WiFi Network

Links to Documentation and Tools
Arduino IDE

https://www.arduino.cc/en/software

ESP32 Board Manager

https://github.com/espressif/arduino-esp32

ESP32 WebServer Documentation

https://randomnerdtutorials.com/esp32-web-server-arduino-ide/

Steps I Followed

First, I installed Arduino IDE and the ESP32 board package. After that, I connected the AI Thinker ESP32-CAM to my computer using a USB cable. Then I selected AI Thinker ESP32-CAM in Arduino IDE and opened the ESP32 WebServer example code. I changed the code to create a fake login webpage and added my WiFi name and password into the code. After uploading the code to the ESP32, I opened Serial Monitor and changed the baud rate to 115200. I pressed the reset button on the ESP32 and copied the IP address shown in Serial Monitor. Then I opened the IP address in my browser and tested the fake login page with usernames and passwords. Finally, I checked Serial Monitor to make sure the login attempts appeared correctly.

Problems and Solutions
Problem
camera_pins.h: No such file or directory
Solution

I was using the wrong example code at first. I fixed it by opening the correct ESP32 WebServer example and selecting the correct board.

Problem
Camera init failed with error 0x106
Solution

The wrong board type was selected. I changed it to AI Thinker ESP32-CAM and uploaded the code again.

Problem

The webpage would not open and kept saying “connection refused.”

Solution

The web server was not starting correctly in the code. I fixed it by adding the correct server.begin(); line and webpage routing functions.

Problem

Nothing showed up in the Serial Monitor after uploading the code.

Solution

I changed the baud rate to 115200 and pressed the reset button on the ESP32.

Problem

The ESP32 kept showing dots and would not connect.

Solution

The WiFi name and password were entered wrong in the code. After fixing them and uploading the code again, the ESP32 connected successfully.

Final Report

This project showed how an ESP32 can host a fake login webpage using a web server. The project demonstrated how phishing and fake login pages can collect usernames and passwords. During this project I learned how to set up ESP32 boards, connect devices to WiFi, host a web server, and troubleshoot connection and coding problems.
