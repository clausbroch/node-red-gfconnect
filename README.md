Node Red GFConnect
===========

### About
Node Red GFConnect is a Node-RED flow for connecting with the Grainfather Connect (G30) brewing system.

<img src="pictures/GFConnectMainControl.png">

The following features are currently supported:
* Temperature control
* Pump control
* Heating power control
* Timer control (stop, pause, resume)
* Push notifications via Pushover

### Dependencies
* node-red-dashboard v3.1.0
* node-red-contrib-ui-level v0.1.27
* node-red-contrib-generic-ble v2.19.4
* node-red-node-rbe v0.2.8

### Configuring Push Notifications

<img src="pictures/GFConnectSettings.png">

GF Connects support push notifications which are delivered via the Pushover App.

To set up push notifications for brew events, e.g. when a timer expires, you will need to enter your Pushover user key and API key into the Notification settings. You will need to register for a new API Key in Pushover. It is also possible to use a group key instead of a user key so more than one user can receive the notifications.

The Pushover keys are avaliable through the [Pushover Dashboard](https://pushover.net/)

### Contributions
* [Claus Broch](https://github.com/clausbroch) - Main author of the Node RED flow for connecting to Grainfather
* [Kingpulsar](https://github.com/kingpulsar) - This project wouldn't have been possible without his reverse engineering of the Grainfather bluetooth protocol - See [kingpulsar/Grainfather-Bluetooth-Protocol](https://github.com/kingpulsar/Grainfather-Bluetooth-Protocol) for more information

### License
This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
