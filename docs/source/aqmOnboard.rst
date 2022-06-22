AQM-Onboard
===========

Introduction
------------

   This is the actual software that runs on the ESP32-Microcontroller and does all the "heavy lifting". 
   It reads sensor values from the Infineon/Cypress Sensorboard via Bluetooth. The values are then sent
   to a MQTT-Broker in JSON format.

   Additionally, a small Web Interface with OTA-Functionality is included. Every network activity runs over
   HTTPS/TLS and is therefore fully encrypted.

GitHub
------

   You can check out the code here:
   https://github.com/felixslama/aqm

