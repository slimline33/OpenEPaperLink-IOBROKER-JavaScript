# OpenEPaperLink JavaScript for IOBROKER

Unfortunately, the original adapter for the iobroker is no longer being developed. I have therefore written a script that retrieves the data. It can't do more than retrieve, but it reacts to the buttons accordingly. 

Simply create a new JavaScript with the content of the script. Change the IP address to that of an access point and off you go.

The script creates the folder Open-E-Paper-Link under 0_userdata and in it the displays integrated into the MAC address.

![image](https://github.com/slimline33/OpenEPaperLink-IOBROKER-JavaScript/assets/3323812/be35b6e2-e2fd-44d3-a2e3-af0448ef663e)

Especially the displays (tags) with buttons change the value of “wakeupreason” to 4 or 5 depending on the button pressed. This must then be integrated accordingly in further scripts or blockly and reacted to. 

![image](https://github.com/slimline33/OpenEPaperLink-IOBROKER-JavaScript/assets/3323812/64b703fd-88cf-4491-9676-883750a06da7)

WebSocket Connection: Connects to the server using WebSockets and handles events such as open, message receive, close, and error.

Ping/Pong Heartbeat: The script sends a ping every 10 seconds to keep the connection active and receives pong messages.

Data Processing: Parses incoming data and processes it accordingly.

Data Point Creation: For each relevant value in the incoming data stream, a corresponding data point is created in ioBroker.

Non-writable States: All created states are set as "non-writable" (write: false) to prevent them from being modified by the user interface or other scripts.

Dynamic Retrieval and Setting of Additional Data:

Fetching device dimensions (height and width) based on the hwType.
Converting the hwType into an uppercase hexadecimal string for the filename.
Storing additional data such as name, colors, and colortable from an external JSON file based on the hwType.
Automatic Reconnection: In case of connection disruptions, the script attempts to reconnect automatically every 5 seconds.

Error Handling: Extensive error handling throughout the data processing, including logging errors for HTTP requests or data parsing.
