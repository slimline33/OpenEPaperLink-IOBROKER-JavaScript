# Open-E-Paper-Link-JS
A Script for receiving the websocket from the open e-paper link project.

Unfortunately, the original adapter for the iobroker is no longer being developed. I have therefore written a script that retrieves the data. It can't do more than retrieve, but it reacts to the buttons accordingly. 

Simply create a new JavaScript with the content of the script. Change the IP address to that of an access point and off you go.

The script creates the folder Open-E-Paper-Link under 0_userdata and in it the displays integrated into the MAC address.

![image](https://github.com/slimline33/Open-E-Paper-Link-JS/assets/3323812/ff82ffe3-96a3-4ec9-8fe3-d33d2c3327f7)

Especially the displays (tags) with buttons change the value of “wakeupreason” to 4 or 5 depending on the button pressed. This must then be integrated accordingly in further scripts or blockly and reacted to. 

![image](https://github.com/slimline33/Open-E-Paper-Link-JS/assets/3323812/489969ac-c752-4167-8aed-6b1fde71e02c)
