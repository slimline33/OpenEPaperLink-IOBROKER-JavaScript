# OpenEPaperLink JavaScript for IOBROKER

Unfortunately, the original adapter for the iobroker is no longer being developed. I have therefore written a script that retrieves the data. It can't do more than retrieve, but it reacts to the buttons accordingly. 

Simply create a new JavaScript with the content of the script. Change the IP address to that of an access point and off you go.

The script creates the folder Open-E-Paper-Link under 0_userdata and in it the displays integrated into the MAC address.

![image](https://github.com/slimline33/OpenEPaperLink-IOBROKER-JavaScript/assets/3323812/be35b6e2-e2fd-44d3-a2e3-af0448ef663e)

Especially the displays (tags) with buttons change the value of “wakeupreason” to 4 or 5 depending on the button pressed. This must then be integrated accordingly in further scripts or blockly and reacted to. 

![image](https://github.com/slimline33/OpenEPaperLink-IOBROKER-JavaScript/assets/3323812/64b703fd-88cf-4491-9676-883750a06da7)

**Benefits:**

1. WebSocket Connection: Connects to the server using WebSockets and handles events such as open, message receive, close, and error.

2. Ping/Pong Heartbeat: The script sends a ping every 10 seconds to keep the connection active and receives pong messages.

3. Data Processing: Parses incoming data and processes it accordingly.

4. Data Point Creation: For each relevant value in the incoming data stream, a corresponding data point is created in ioBroker.

5. Non-writable States: All created states are set as "non-writable" (write: false) to prevent them from being modified by the user interface or other scripts.

6. Dynamic Retrieval and Setting of Additional Data:
6.1 Fetching device dimensions (height and width) based on the hwType.
6.2 Converting the hwType into an uppercase hexadecimal string for the filename.
6.3 Storing additional data such as name, colors, and colortable from an external JSON file based on the hwType.

7. Error Handling: Extensive error handling throughout the data processing, including logging errors for HTTP requests or data parsing.

# OpenEPaperLink Weather Image from chatGTP

This script is designed to fetch the current weather for a specified city using the OpenWeatherMap API, generate an artistic image based on the weather condition using the DALL-E 3 model, resize the generated image, and log the entire process. The script is configured to run automatically every day at 5 AM.

**Key Features:**

Uses the OpenWeatherMap API to fetch the current weather description for a specified city.
Logs the weather data fetched successfully or any errors encountered during the fetch.
Generate Image with DALL-E 3.

Depending on the weather condition, it creates a specific prompt to generate an image using the DALL-E 3 model.
The prompt includes specific instructions to use only three colors (black, white, and red) and ensures the mood matches the weather condition (e.g., cheerful for sunny weather, creepy for thunderstorms).
Sends a request to the DALL-E 3 API to generate the image based on the prompt.
Logs the URL of the generated image and any errors encountered during the process.

**Check for Weather Chang:**

Compares the current weather description with the last recorded weather condition. If the weather has changed, it triggers the image generation process and updates the last recorded weather file.
Logs whether a new image generation was necessary based on the weather change. 

**Scheduled Execution**

Configured to run daily at 5 AM to fetch the latest weather data and update the image if necessary.

**SETTINGS**

WEATHER_API_KEY: API key for accessing OpenWeatherMap.
CHATGPT_API_URL: URL endpoint for accessing the DALL-E 3 API.
CHATGPT_API_KEY: API key for accessing the DALL-E 3 model.

**Paths and File Locations:**

BASE_PATH: Base path for storing files.
LAST_WEATHER_FILE: Path to store the last recorded weather condition.
IMAGE_SAVE_PATH: Path to save the initially generated image.
IMAGE_RESIZED_PATH: Path to save the resized image.
LOG_FILE_PATH: Path to save the log file.

**Image Dimensions:**

IMAGE_WIDTH and IMAGE_HEIGHT: Dimensions for the generated image.

**Libraries and Tools Used:**

axios: For making HTTP requests to the OpenWeatherMap and DALL-E 3 APIs.
fs (File System): For reading and writing files.
path: For handling file paths.
winston: For logging the process and errors.

**Fetch Current Weather Data:**

Send a request to the OpenWeatherMap API. Log the fetched weather data or errors. Generate Image Based on Weather.

Create a prompt based on the weather condition. Send a request to the DALL-E 3 API to generate the image. Save the generated image and log the process.

**Check Weather Change:**

Compare the current weather with the last recorded weather. If the weather has changed, generate a new image and update the last weather record. Log whether a new image was generated.

Run the entire script daily at 5 AM to ensure the image is up-to-date with the current weather.
This script automates the process of generating and updating an artistic representation of the current weather, making it suitable for use in applications like digital displays or weather dashboards.
