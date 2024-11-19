A development of CANBUS yaml code for use in ESPHome and Home Assistant, to expose Vehicle based data and entities for automation and monitoring.
** This Code is specific for the Peugeot Boxer MkIII and has no been tested on any other make / model **
(but should in theory work on Fiat Ducato and Citreon Relay models)

Hardware:
ESP32-WROOM-Devkit v1
TJA1050 canbus transciever (5v)

Using a 5v powered ESP32-WROOM-DEvkit, wired with the Tx/Rx pins connected to a TJA1050 Canbus transceiver board. (with 5v power).
the TJA1050 CAN High and Low are connected to the CAN-H (Blue) and CAN-L (White) wires on the back of the OEM Stereo - or to pins 1&9 on the ODB diagnostics port.

refer to <esp32-taj1050.jpg> in the files.

The CANbus that is exposed on the rear of the Stereo and ODB Port Pins 1&9, is a low speed BSI connected data bus, used to communicate with the BSI/BCM 
(Interfacing to Engine ECU, TPMS, Door Locks, etc) controlling , Instrument Cluster and Stereo.

The CANbus messages are sent at 50Kbps on the low speed B-CAN bus, in 29bit Hex format.

Typical messages that are sent on this bus are
  Vehicle Speed
  Door Lock Status
  Fuel Level
  Engine RPM
  Media/Volume Controls
  Date/Time Clock

It is therefore possible to intercept this traffic and create Sensors in ESPhome, integrating the data into Home Assistant.

A few options exist to `sniff` the canbus messages, for my project i purchased a WiCAN USB module which was easy to 
setup and get started without having to first develop my own CANbus ESP device.



