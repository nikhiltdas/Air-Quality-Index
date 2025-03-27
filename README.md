# Air Quality Index

This system collects air quality data (temperature, humidity, and gas levels) using an ESP32 microcontroller and sensors. The data is then transmitted to AWS IoT Core using MQTT for reliable message queuing. A separate application (e.g., a Python script or AWS Lambda function) retrieves the data from AWS IoT Core and stores it in a MongoDB database. This allows for real-time monitoring and historical data analysis.

## Hardware Components

-   ESP32 Development Board
-   DHT11 Temperature and Humidity Sensor
-   MQ6 Gas Sensor (for detecting combustible gases like LPG, propane, etc.)
-   Breadboard and Jumper Wires

## Software Components

-   Arduino IDE (for ESP32 firmware)
-   AWS IoT Core
-   MongoDB Atlas (or local MongoDB instance)
-   Node JS (for data processing and storage)
-   Arduino Libraries:
    -   DHT sensor library (e.g., DHT sensor library by Adafruit)
    -   PubSubClient (for MQTT communication)

## Setup Instructions

### Hardware Setup

1.  Connect the DHT11 and MQ6 sensors to the ESP32 according to the following wiring diagram (or your preferred pin configurations).
2.  Power the ESP32 using a USB cable or external power supply.


### AWS IoT Core Setup

1.  Create an AWS account and navigate to the AWS IoT Core service.
2.  Create a "Thing" in AWS IoT Core.
3.  Generate and download the certificates (private key, certificate, and root CA) for the Thing.
4.  Create an IoT policy that grants the Thing permissions to connect, publish, and subscribe to MQTT topics.
5.  Note the AWS IoT Core endpoint.

### MongoDB Setup

1.  Create a MongoDB Atlas account (or set up a local MongoDB instance).
2.  Create a database and collection to store the sensor data.
3.  Obtain the MongoDB connection string.

### ESP32 Firmware Setup

1.  Install the Arduino IDE and ESP32 board support.
2.  Install the required Arduino libraries (DHT, PubSubClient).
3.  Copy the AWS IoT Core certificates to the ESP32's SPIFFS or embed them in the code.
4.  Configure the ESP32 code with your Wi-Fi credentials, AWS IoT Core endpoint, Thing name, and MQTT topic.
5.  Upload the firmware to the ESP32.

### Data Processing and Storage Setup

2.  Create a node script (or AWS Lambda function) that subscribes to the MQTT topic on AWS IoT Core.
3.  Parse the received data and store it in the MongoDB database.
4.  Configure the script with the MongoDB connection string and database/collection names.

## Usage

1.  Power on the ESP32.
2.  The ESP32 will connect to Wi-Fi and AWS IoT Core, and start publishing sensor data to the MQTT topic.
3.  The node script will receive the data and store it in MongoDB.
4.  You can then query the MongoDB database to analyze the collected data.
5. You can also use Mongocharts to display the data in a visual format or any other chart applications.

In parallel I used to conduct a survey in students of the classroom. The survey consist of the following questions:

1. Are you experiencing any discomfort due to the temperature in the classroom?
 Very often
 Often
 Sometimes
 Never
 Low

2. Have you often encounter with headache while in classroom?
 Very often
 Often
 Sometimes
 Never
 Low

3. Do you have difficulty concentrating or feel fatigued?
 Very often
 Often
 Sometimes
 Never

4. Have you noticed any unusual odors or tastes in your classroom?
 Very often
 Often
 Sometimes
 Never

5. Have you noticed any changes in your mood or emotional well-being related to certain
environmental conditions?
 Yes

 No
6. Do you think your classroom has adequate supply of light and air?
 Yes

 No
7. Are there any noticeable sources of indoor air pollution in your classroom? (e.g., strong
odors, dust, mold)
Very High
High
Moderate Low

8. How often do you attend classes in this classroom?
 Daily
 Weekly
 Monthly
 Not have a proper cycle

 9. Have you taking any medicines which alters your normal hormonal balance?
Yes
No

### IBM SPSS Statistics is a powerful statistical software suite developed by IBM. It's widely used by researchers, analysts, and businesses to perform various statistical analyses and data management tasks. 
## What is IBM SPSS Statistics?
1. It's a comprehensive software package designed for:
2. Data management: Handling and organizing data.   
3. Statistical analysis: Performing various statistical tests and procedures.   
4. Data visualization: Creating charts and graphs to represent data

   ### SPSS Integration

1.  Install IBM SPSS Statistics.
2.  Export the data from MongoDB to a CSV file (or another format compatible with SPSS). You can use python and the pymongo library to achieve this.
3.  Import the CSV file into SPSS.
4.  Use SPSS to perform data visualization (e.g., charts, graphs) and statistical analysis (e.g., descriptive statistics, correlations, regressions).
5.  Document the analysis and visualizations generated in SPSS.
