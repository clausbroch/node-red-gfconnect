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
* Loading of brew session from Brewfather batch json files
* Sending timer and brew alerts as push notifications via Pushover

### Dependencies
* node-red-dashboard
* node-red-contrib-ui-level
* node-red-contrib-generic-ble
* node-red-node-rbe

### Brew Sessions

In order to start a brew session you first need to establish a connection between the Grainfather controller and GF Connect. Then you navigate to the Brewfather File upload panel and upload the batch json file you have downloaded from the [Brewfather](https://web.brewfather.app/tabs/batches) brew planner website.

<img src="pictures/BrewfatherFileUpload.png">

Once you click the "Upload" button, the recipe will be sent to the Grainfather controller and you can start brewing:

<img src="pictures/GFConnectBrewSessionStartHeating.png">

You will now be able to control the brew session from the GFConnect panel or from the Grainfather controller.

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
