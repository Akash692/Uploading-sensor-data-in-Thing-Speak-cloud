Uploading temperature sensor data in Thing Speak cloud
NAME:Akash

REG NO:24900964

AIM:
To monitor the temperature sensor data in the Thing speak using an ESP32 controller.

Apparatus required:
ESP32 Controller
Temperature Sensor
Power supply
Connecting wires
Bread board

PROCEDURE:
Arduino IDE
Step1:Open the Arduino IDE
Step2: Go to sketch- include library – manage libraries file and install esp32 and thing speak library file
Step3:Go to file and select new file option
Step4:Type the program and update the thing speak channel ID, API key, wifi password and ID
Step5:Go to file and select save option to save the program
Step6:Go to sketch and select verify or compile options
Step7:If no error Hex file will be generated in the temporary folder
Step8: Connect all the components as per the circuit diagram
Step9: Connect the programming cable with esp32 and PC.
Step10: Check the jumper position and connect 4 & 5 of P4.
Step11. Upload the program in the esp32.
Step12 Press the boot button in ESP32 and then press and release the reset button after release the boot button
Step13 Check the output in the cloud

Thingspeak
Step1 Create a ThingSpeak Account
Step2 Log in to your ThingSpeak account
Step3 Create a new channel by navigating to "Channels" and clicking on "New Channel."
Step4 Configure your channel settings, such as Field labels and Channel name
Step5 Copy the Channel ID and API key in the thingspeak and update in the program
Step6 Execute your program to send the sensor value to ThingSpeak
Step7 Check your ThingSpeak channel to verify that the sensor value has been updated

THEORY:
What is IoT?
Internet of Things (IoT) describes an emerging trend where a large number of embedded devices (things) are connected to the Internet. These connected devices communicate with people and other things and often provide sensor data to cloud storage and cloud computing resources where the data is processed and analyzed to gain important insights. Cheap cloud computing power and increased device connectivity is enabling this trend.IoT solutions are built for many vertical applications such as environmental monitoring and control, health monitoring, vehicle fleet monitoring, industrial monitoring and control, and home automation

image

Sending Data to Cloud with ESP32 and ThingSpeak
ThingSpeak is an Internet of Things (IoT) analytics platform that allows users to collect, analyze, and visualize data from sensors or devices connected to the Internet. It is a cloud-based platform that provides APIs for storing and retrieving data, as well as tools for data analysis and visualization.The Internet of Things ( or IoT) is a network of interconnected computing devices such as digital machines, automobiles with built-in sensors, or humans with unique identifiers and the ability to communicate data over a network without human intervention.Hello readers, I hope you all are doing great. In this tutorial, we will learn how to send sensor readings from ESP32 to the ThingSpeak cloud. Here we will use the ESP32’s internal sensor like hall-effect sensor and temperature sensor to observe the data and then will share that data cloud.

What is ThingSpeak?
image

It is an open data platform for IoT (Internet of Things). ThingSpeak is a web service operated by MathWorks where we can send sensor readings/data to the cloud. We can also visualize and act on the data (calculate the data) posted by the devices to ThingSpeak. The data can be stored in either private or public channels.ThingSpeak is frequently used for internet of things prototyping and proof of concept systems that require analytics.

Features Of ThingSpeak
ThingSpeak service enables users to share analyzed data through public channels:
ThingSpeak allows professionals to prepare and analyze data for their businesses:
ThingSpeak updates various ThingSpeak channels using MQTT and REST APIs:
Easily configure devices to send data to ThingSpeak using popular IoT protocols.
Visualize your sensor data in real-time.
Aggregate data on-demand from third-party sources.
Use the power of MATLAB to make sense of your IoT data.
Run your IoT analytics automatically based on schedules or events.
Prototype and build IoT systems without setting up servers or developing web software.
Automatically act on your data and communicate using third-party services like Twilio® or Twitter®

image

PROGRAM:
const int trigPin = 9;
const int echoPin = 10;

long duration;
int distance;
void setup() {
pinMode(trigPin, OUTPUT);
pinMode(echoPin, INPUT);
Serial.begin(9600);
}

void loop() 
{
  digitalWrite(trigPin, LOW);
  delayMicroseconds(2);
  digitalWrite(trigPin, HIGH);
  delayMicroseconds(10);
  digitalWrite(trigPin, LOW);
  duration = pulseIn(echoPin, HIGH);
  distance= duration*0.034/2;
  Serial.print("Distance: ");
  Serial.println(distance);
}
CIRCUIT DIAGRAM:
Screenshot 2024-12-09 185712

OUTPUT:
Screenshot 2024-12-09 185724

RESULT:
Thus the temperature sensor values are updated in the Thing speak using ESP32 controller.
