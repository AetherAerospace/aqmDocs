AQM-CredMan
===========

Introduction
------------

   AQM Credman (Credential Manager) is an Azure Function that is used to obtain credentials for the building process

GitHub
------

   You can check out the code here:
   https://github.com/felixslama/aqmCredentialManager

Quick Overview
--------------

   The AQM-CredMan runs on Azure and gets its configuration values from the function owner.

   During the start of the function, a secret will be generated and shown to the function owner.

   This secret can than be imported to any TOTP app. The app will then be able to generate a six-digit numeric code used by the configurator.

TOTP
----
   AQM-CredMan uses the pyotp library for otp creation and verification. 
   Once the function receives a code, the function will try to verify the code.

   If the code is correct, the client will receive a message in JSON-Format which can than be used by the Configurator.
