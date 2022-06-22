AQM-Configurator
================

Introduction
------------

   To make Flashing and Credential management easier, we have developed a simple
   pyQT-Application that handles these things for us.

Installation
------------

Follow the Steps below to Prepare, Build and Flash the newest Version of AQM onto your ESP32

Requirements
^^^^^^^^^^^^

   You will need to have the following things installed:

   - Python3
   - pip
   - PlatformIO Core

Preperation
^^^^^^^^^^^

   1. Clone the aqmConfigurator Repository

   .. code-block:: console

      $ git clone https://github.com/felixslama/aqmConfigurator.git
      $ cd aqmConfigurator/

   (Alternatively just download it as .zip and unzip it)

   2. Install the needed requirements

   .. code-block:: console

      $ pip install -r requirements.txt

Usage
^^^^^

   If you followed the above Steps correctly, you should be able to launch the Configurator now

   .. code-block:: console

      $ python aqmConf.py

   It should look something like this
      
   .. image:: img/configurator.png
      :scale: 100 %
      :align: center

Obtaining Credentials
^^^^^^^^^^^^^^^^^^^^^

   AQM fetches credentials from a remote Azure Serverless Function using TOTP

   1. Input the OTP-Token into the Input Filed
   2. Press "Submit"
   3. The app will inform you if credentials were obtained or not

Flashing
^^^^^^^^

   .. note::
      The Builing Process **WILL FAIL** if you didnt fetch the credentials first!

   1. Connect your ESP32
   2. Press the "Build" Button
   3. The Building Process will start and flash the ESP32 automatically

   That's it, your done.
