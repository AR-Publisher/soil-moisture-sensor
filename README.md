#Monitor Soil Moisture Sensor Data with Nodemcu on Thingspeak
In this project, we are going to interface Resistive Soil Moisture Sensor with NodeMCU ESP8266 & OLED Display & Monitor Soil Moisture Data on Thingspeak Server.
Table of Contents 
1)	Overview
2)	Bill of Materials
3)	Resistive Soil Moisture Sensor
a.	Working of Resistive Soil Moisture Sensor
4)	Interfacing Resistive Soil Moisture Sensor with Nodemcu & OLED Display
5)	Monitoring Soil Moisture Sensor Data with Nodemcu on Thingspeak
6)	Source Code/Program
7)	Results & Observations
Overview
In this post, we are going to interface a Resistive Soil moisture sensor FC-28 with Nodemcu ESP8266 Board & 0.96″ OLED Display. This sensor measures the volumetric content of water inside the soil and gives us the moisture level as output. The sensor is equipped with both analog and digital output, so it can be used in both analog and digital modes. Here we will use the sensor in Analog mode and measure the soil moisture in percentage.
The measured soil moisture can be sent to any IoT cloud platform. In this case, we will use Thingspeak Server. Thinspeak server is an open data platform and API for the Internet of Things that enables you to collect, store, analyze, visualize, and act on data from sensors. The soil moisture data from Soil Moisture Sensor can be monitored online from any part of the world.
Bill of Materials
Following are the components required for making this project. All the components can be purchased from Amazon. The components purchased link is given below.
S.N.	COMPONENTS NAME	QUANTITY
1	NodeMCU ESP8266	1
2	0.96" I2C OLED Display	1
3	Connecting Wires	10
4	Breadboard	1
5	Soil Moisture Sensor	1



Resistive Soil Moisture Sensor
The soil Moisture sensor FC-28 consists of two probes that are used to measure the volumetric content of water. The sensor works between the input voltage range of 3.3V to 5V. The output voltage given by it is 0 – 4.2V. The output signal appears both in analog form and in digital form.
The soil Moisture sensor FC-28 has four pins
VCC: For power
A0: Analog output
D0: Digital output
GND: Ground
The Module also contains a potentiometer that will set the threshold value and then this threshold value will be compared by the LM393 comparator. The output LED will light up and down according to this threshold value.
Working of Resistive Soil Moisture Sensor
The soil moisture sensor consists of two probes that are used to measure the volumetric content of water. The two probes allow the current to pass through the soil and then it gets the resistance value to measure the moisture value.
When there is more water, the soil will conduct more electricity which means that there will be less resistance. Therefore, the moisture level will be higher. Dry soil conducts electricity poorly, so when there will be less water, then the soil will conduct less electricity which means that there will be more resistance. Therefore, the moisture level will be lower.
________________________________________
Interfacing Resistive Soil Moisture Sensor with Nodemcu & OLED Display
Here is a circuit diagram for interfacing Resistive Soil Moisture Sensor with Nodemcu ESP8266 Board. The connection is fairly simple.
We are using the soil moisture sensor in analog mode. So, connect the analog output pin to A0 of Nodemcu. Similarly, OLED Display is an I2C Module. So, connect its SDA SCL pin to D2 & D1 of Nodemcu. Both the OLED & Soil Moisture Sensor work at 3.3V. So connect their VCC pin to 3.3V of Nodemcu.
Monitoring Soil Moisture Sensor Data with Nodemcu on Thingspeak
In order to Monitor the Sensor Data on Thingspeak Server, you first need to Setup the Thingspeak. To setup the Thingspeak Server, visit https://thingspeak.com/. Create an account or simply sign in if you created the account earlier. Then create a new channel.

Source Code/Program
Find the source code/program below for the Resistive Soil Moisture Sensor with OLED Display. You need to add two libraries for the code compilation.
1. Adafruit_SSD1306 : https://github.com/adafruit/Adafruit_SSD1306
2. Adafruit_GFX : https://github.com/adafruit/Adafruit-GFX-Library
Make sure to change the Wifi SSID & Password. Also, change the API key here.

Results & Observations
Once the code is uploaded you can open the serial monitor and see the following.

Now you can dip the soil moisture probe in mud and see the value on OLED Screen or Serial Monitor. The more wet the soil the more the soil moisture percentage. Drier the soil, less the soil moisture percentage.
Now you can log into your thingspeak account. Then go to the private view. In the private view, you can see Thingspeak data getting uploaded after the interval of 15 seconds.
