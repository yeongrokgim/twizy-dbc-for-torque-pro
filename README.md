# Twizy DBC for Torque Pro

An approach to display status of Renault Twizy with an Android device, using Torque Pro app.

## Background

Usually most of contemporary vehicle is compatible with OBD-II standard, especially comply with ISO 15031-5 standards. Basically a diagnostic devices make an request by publishing a packet to the CAN bus, then device of interest, such as ECU, TCU, make a response packet to the bus, then diag device catches then displays useful information.

Renault Twizy has quite different approach. They do support request-response based communication for SEVCON device, (see [Twizy-Cfg](https://github.com/dexterbg/Twizy-Cfg) repository) but most of useful information is just broadcasted into bus without any request made.

This difference breaks compatibilty of most OBD-II diagnostic devices or application.

## Prerequisites

What I have tested:

- ELM327 bluetooth adapter (BLE device).
- An Android device with bluetooth connection.
- Torque Pro app from Google Play Store

I tested 4 different bluetooth adapters, but only one was compatible. Others were not responding to `AT I` command, presumably because they all are partially-compatible emulators of genuine ELM327 chips

## Configuration

- Install Torque Pro app
  - Create a vehicle profile for Twizy
  - Set it to use CAN bus monitor mode, as we will just listen CAN bus without making any request.
- Download DBC file, import.

## References and further readings

- https://play.google.com/store/apps/details?id=org.prowl.torque
- Twizy CAN bus objects (AFIAK Credit: [@dexterbg](https://github.com/dexterbg))https://docs.google.com/spreadsheets/d/1gOrG9rnGR9YuMGakAbl4s97a6irHF6UNFV1TS5Ll7MY/
- https://docs.openvehicles.com/en/latest/components/vehicle_dbc/docs/dbc-primer.html
