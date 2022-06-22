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

Quick Overview
--------------

   On startup, the ESP32 establishes a connection to the Sensorboard.
   Once the connection is established, the ESP32 waits for the Sensorboard to send its meassured values.
   By default, this happens every two seconds.

   After the ESP32 received the data, it starts building the MQTT-Message in JSON format.
   This message is then published to the MQTT-Broker specified in the configuraton file.

   Now everyone subscribed to the MQTT-Topic can see the current sensor values and use them however they want.

OverTheAir-Update
-----------------

   Because AQM is designed to be deployed in remote locations, we added the OTA-Functionality.

   On startup, the ESP32 opens a webserver on port 443(HTTPS), in this webinterface, admins with the correct credentials can login and upload a .bin file.

   The entire process is encrypted and therefore save to use, even in public networks.
   Once the .bin file is completly transfered to the ESP32 it will apply the update and reboot.
   
   .. note::
      In case the update fails, the ESP32 will just return to the old, working firmware version.

Code
----
   The code is onboard-code is devided in five files.

   #. **MQTT**

      ``This file contains everything MQTT related.``
   #. **BLE**

      ``As the name suggests, this part contains everything Bluetooth Low Entergy (BLE) related.``
   #. **Web**

      ``Everything needed for the Webserver and OTA-Functionality can be found in this file``
   #. **WiFi**

      ``In here, there are two functions. One for private networks, secured by WPA2 or WPA3 and one function for WPA-Enterprise with username and password.``
   #. **Utility**

      ``In the utility file there are just a few helper functions. One of which provides a timestamp in the correct format for the MQTT-Message``