Node Red GFConnect
===========

## About
Node Red GFConnect is a Node-RED flow for controlling the Grainfather Connect (G30) brewing system from Raspberry Pi. It can be used as a replacement for the official Grainfather App.

<img src="pictures/GFConnectMainControl.png">

The following features are currently supported:
* Temperature control
* Pump control
* Heating power control
* Timer control (set, stop, pause, resume)
* Delayed heat control (set, stop, pause, resume)
* Loading of brew session from Brewfather batch json files
* Loading of brew session directly from Brewfather (preliminary Brewfather support)
* Delayed start of brew sessions
* Sending timer and brew session alerts as push notifications via Pushover

## Dependencies
* node-red-dashboard
* node-red-contrib-ui-level
* node-red-contrib-noble-bluetooth
* node-red-node-rbe

## Installation

If you already have Node-RED installed you can install GFConnect by copying the content of the [flow.json](flow.json) file into the workspace by selecting the menu "Import" -> "Clipboard":

<img src="pictures/InstallFlow.png"></img>

Paste the content of flow.json into the "Import nodes" dialog, select to import to "new flow" and click the "Import" button.

<img src="pictures/ImportNewFlow.png"></img>

In the workspace click the "Deploy" button to deploy the flow to the Node RED server. 

If you do not have Node-RED installed, you can follow [this detailed guide](https://www.norgesvej12a.dk/husbryg/setting-up-a-new-raspberry-pi-zero-w-for-gf-connect/) for how to install the software on a new Raspberry Pi Zero W.

The GFConnect dashboard can now be accessed from http://pi:1880/ui/ where *pi* is either the hostname or the ip address of your Raspberry Pi.

## Brew Sessions

In order to start a brew session you first need to establish a connection between the Grainfather controller and GF Connect. Then you navigate to the Brewfather File upload panel and upload the batch json file you have downloaded from the [Brewfather](https://web.brewfather.app/tabs/batches) brew planner website.

<img src="pictures/BrewfatherFileUpload.png">

Click the "Upload File" button to load the recipe into the Raspberry Pi.

It is also possible to fetch the recipe directly from Brewfather. First click the "Refresh List" button to fetch a list of batches that are ready for brewing ("Planned" or "Brewing" status). Next select the batch from the drop down list to load it into the Raspberry Pi.

In order to use the direct Brewfather integration feature you need to generate your API/User Key directly from the [Brewfather settings page](https://web.brewfather.app/tabs/settings) and enter these in the GF Connect settings. Make sure you generate the key to allow both read and write access to the Batch feature.

Once the recipe is loaded, you can start the brew session by clicking "Start Session". Alternatively you can delay the session start by setting the number of hours and minutes and clicking the "Start Delayed Session". The recipe will now be sent to the Grainfather controller and you can start brewing:

<img src="pictures/GFConnectBrewSessionStartHeating.png">

You will now be able to control the brew session from the GFConnect panel or from the Grainfather controller.

## Configuring Push Notifications

<img src="pictures/GFConnectSettings.png">

GF Connects support push notifications which are delivered via the Pushover App.

To set up push notifications for brew events, e.g. when a timer expires, you will need to enter your Pushover user key and API key into the Notification settings. You will need to register for a new API Key in Pushover. It is also possible to use a group key instead of a user key so more than one user can receive the notifications.

The Pushover keys are avaliable through the [Pushover Dashboard](https://pushover.net/)

## Contributions
* [Claus Broch](https://github.com/clausbroch) - Main author of the Node RED flow for connecting to Grainfather
* [Kingpulsar](https://github.com/kingpulsar) - This project wouldn't have been possible without his reverse engineering of the Grainfather bluetooth protocol - See [kingpulsar/Grainfather-Bluetooth-Protocol](https://github.com/kingpulsar/Grainfather-Bluetooth-Protocol) for more information

## License
This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
