# Bee Keeping Firmware
## Hardware components
### 1.Main controller -> ESP32

<p align="center">
	<img src="images/main.jpg" height="500"></img>
	<img  height="500" src="images/mainRender.png"></img>
</p>

- Measure temperature using the onboard ds18b20 sensor
- samples hive 'noise' via i2s using the microphone on the board  
- receive hive weight, ambient temperature and humidity data from aux board via LoRa 
- post the temperature, audio and the aux sensor data to anabi DW server
- logging sensor payload data on post data errors

### 2.Auxilliary board -> atmega328p 

<p align="center">
	<img src="images/aux.jpg" height="500"></img>
	<img  height="500" src="images/auxRender.png"></img>
</p>

- measures weight of the hive with load cells
- measure ambient temperature and humidity using the dht22 
- send data to main board via loRa

## Folder structure
	.
	├── api                 # Api tests files
	|	├── automate.py		# python script to post data to anabi dw server
	|	├── hardwareTest	# Directory containing micropython code for the esp32
			├── c			# C/arduino version of the firmware
			├── micropython	# micropython version of the firmware
			├── pythonTsts	# Api python tests
	|	├── images			# Images
	|	├── creds.txt		#text file containing A0uth credentials
	├── docs                # Documentation files (alternatively `doc`)
	├── images              # Image files
	├── loratests           # arduino and esp32 loratests files     
	├── actions.txt			# Work actions 
	└── README.md

## WebApi
WebApi component provides an access to DW for external systems and components via REST
API. 
<p align="center">
	<img src="images/web.png" height="500"></img>
	<img  height="500" src="images/webauxhum.png"></img>
	<img src="images/webauxtemp.png" height="500"></img>
	<img  height="500" src="images/webmaintemp.png"></img>
	<img  height="500" src="images/webreport.png"></img>
</p>

