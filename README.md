# OpenEPaperLink JavaScript for IOBROKER
A Script for receiving the websocket from the OpenEPaperLink project -> https://github.com/jjwbruijn/OpenEPaperLink

Unfortunately, the original adapter for the iobroker is no longer being developed. I have therefore written a script that retrieves the data. It can't do more than retrieve, but it reacts to the buttons accordingly. 

Simply create a new JavaScript with the content of the script. Change the IP address to that of an access point and off you go.

The script creates the folder Open-E-Paper-Link under 0_userdata and in it the displays integrated into the MAC address.

![image](https://github.com/slimline33/OpenEPaperLink-IOBROKER-JavaScript/assets/3323812/be35b6e2-e2fd-44d3-a2e3-af0448ef663e)

Especially the displays (tags) with buttons change the value of “wakeupreason” to 4 or 5 depending on the button pressed. This must then be integrated accordingly in further scripts or blockly and reacted to. 

![image](https://github.com/slimline33/OpenEPaperLink-IOBROKER-JavaScript/assets/3323812/64b703fd-88cf-4491-9676-883750a06da7)
