# IOT-based-Weather-Monitoring-System-using-MQTT-protocol-and-nodered

## Introduction
### Conventional Weather Monitoring System:
The significance of weather monitoring exists in numerous perspectives. Weather affects a wide range of man's activities, including agriculture, transportation, industries, and leisure time. Man wants to stay updated about the latest weather conditions of any place like a college campus or any other particular building. Since the world is changing so fast there should be easily ascible weather stations.Existing weather monitoring generally uses weather stations that use multiple instruments such as thermometers, barometers,  wind vanes, rain gauge, etc. to measure weather and climate changes. Most of these instruments use simple analog technology which is later physically recorded and stored in a database. This information is later sent to news reporting stations and radio stations where the weather report is given.

### Limitations of the existing system are:
1. Existing weather monitoring systems that are used in the field generally consist of unconventional and heavy machinery.
2. Power requirements are one of many major constraints these instruments are generally cited far from the main power supply.
3. Data that is collected by the instruments needs to be manually transferred from the logger to a  laptop or computer via a cable.

### Smart Weather Monitoring System:
Alternative for this conventional weather monitoring system is Smart Weather Monitoring System which makes use of IoT. There are multiple sensors commercially available that can work in the ‘Smart Weather Monitoring and Real Time Alert system using IoT’ application. Existing IoT based systems utilize sensors such as DHT11 for temperature and humidity measurement, anemometer for wind speed measurement, LDR for light intensity monitoring, UV radiation measurement using GY8511 solar sensor, Carbon monoxide level monitoring using MQ7, soil moisture measurement using Hygrometer, ultrasonic sensor for level measurement of rain water, raindrop sensor for detecting rainfall/snowfall and Arduino microcontroller based cyber-physical interface. The combination of these components creates a robust alert system (for dealing with emergency scenarios) and data logging mechanism which ensures that the alerts are not lost over time when left unattended. Smart weather monitoring system allow a significant advantage over their conventional counterparts in terms of portability, ease of installation and monitoring, allowing complex weather evaluations/predictions, size, compactness, decreased power requirements, ease of interfacing with APIs using Raspberry Pi, creation of an app that links with the physical system and allows linking the system to a web page that logs data allowing its graphical assessment.

## MQTT Protocol
MQTT(Message Queuing Telemetry Transport Protocol) is one of the earliest M2M communication protocols with its introduction in 1999. Developed by IBM’s Andy Stanford-Clark and Arcom Control Systems Ltd (Eurotech)’s Arlen Nipper, it is a lightweight M2M publish/subscribe communication protocol that is designed for constrained network applications. It is a binary protocol with a header size of 2 bytes and maximum allowable message payload is 256 MB. The MQTT client transmits messages to a MQTT broker topic, end-users/clients that are subscribed to the topic receive these updates or they can be stored for future subscription. With a default TCP transport protocol and TLS/SSL security protocol combined with multi-topic subscription utility makes it a connection-oriented protocol. MQTT offers three QoS levels for reliable message transmission. We have chosen MQTT as our choice of IoT communication protocol because of its suitability for large networks of small devices(temperature sensor in our smart weather monitoring application)  that requires monitoring on a back-end Internet server implemented using Node Red servers.
The publish-subscribe model used in MQTT is different from the traditional client-server model. It separates the client (publisher) that sends the message from the client (subscriber) that receives the message. The publisher and the subscriber do not need to establish direct contact. We can either let multiple publishers publish messages to one subscriber, or let multiple subscribers receive messages from one publisher at the same time. The essence of it is that an intermediate role called a broker is responsible for all message routing and distribution. The traditional client-server model can achieve similar results, but it cannot be as simple and elegant as the publish subscribe model.

![MQTT_Schema_EN-4811768](https://user-images.githubusercontent.com/62541787/127277120-b200f15a-6e31-40ad-b4d2-e4a6c3b0f5a9.jpg)

## Software Used
### Arduino IDE
We used arduino ide to program nodemcu esp8266. The Arduino Integrated Development Environment (IDE) is a cross-platform application (for Windows, macOS, Linux) that is written in functions from C and C++. It is used to write and upload programs to Arduino compatible boards, but also, with the help of third-party cores, other vendor development boards. This software can be used with any Arduino board. The source code for the IDE is released under the GNU General Public License, version 2. The Arduino IDE supports the languages C and C++ using special rules of code structuring. The Arduino IDE supplies a software library from the Wiring project, which provides many common input and output procedures. User-written code only requires two basic functions, for starting the sketch and the main program loop, that are compiled and linked with a program stub main() into an executable cyclic executive program with the GNU toolchain, also included with the IDE distribution.The Arduino IDE employs the program avrdude to convert the executable code into a text file in hexadecimal encoding that is loaded into the Arduino board by a loader program in the board's firmware.By default, avrdude is used as the uploading tool to flash the user code onto official Arduino boards.

### Amazon Web Services(AWS)
AWS is a secure cloud services platform, offering compute power, database storage, content delivery and other functionality to help businesses scale and grow. Amazon Web Service is a Platform as a Service type of cloud. Here, service refers to the development environment and packages/subsystems that form a part of it.  Users are involved in the distribution, development and testing of their own applications but the infrastructure is provided by the service provider which is Amazon Web Service in this case.
In simple words AWS allows you to do :
1. Running web and application servers in the cloud to host dynamic websites.
2. Securely store all your files on the cloud so you can access them from anywhere.
3. Using managed databases like MySQL, Oracle or SQL Server to store information.
4. Deliver static and dynamic files quickly around the world using a Content Delivery Network (CDN).
5. Send bulk email to your customers.

### Node-Red Services
Flow editing and visual programming is a key aspect of IoT. It helps in hosting the entire IoT network on a vast variety of platforms ensuring ease of access for future development. The concept of flow editing involves using Visual data flow programming Languages(VDFPLs) that define all the server components: input, output and functions as a series of nodes interconnected by arcs to form a graphical network for the visual representation of data exchange. The VDFPLs help a non-programmer to gain an intuitive understanding of the IoT placed on the cloud. To implement flow editing, an open-source web-based/browser-based tool called Node-RED is available. Node-RED works hand in hand with JavaScript, using it in its event model, client editor and server along with providing native support for it. The data-flow structures in Node-RED are called ‘flows’ composed of wire-connected ‘nodes’. The basic interface consists of an easy to access flow editor with flow templates provided on the left hand side. These flow templates can be dragged and dropped onto the flow canvas, with all users managing a single Node-RED flow. The creation of a flow is followed by its deployment, which implies the saving and then re-execution of the flow on the Node-RED server. Nodes are members of two JavaScript classes: Node base class and EventEmitter subclass (in Node.js event API). Upon initialization , the nodes may subscribe to external services and receive data on ports or begin processing HTTP requests. Upon completion of data processing by a node, either from an external service or upon reception from an upstream node, base class Node send() is called with a JavaScript object. The send method works in tandem with the EventEmitter.emit() method to send named events to downstream node instances that process data and get involved in generation of additional events, or allow for communication with outside services or OS. The community Node-RED support involves IBM and a plethora of users that contribute new nodes and flows. The implementation of new nodes can be done in JavaScript and their addition can be done via the addition of an HTML file to implement browser UI, and a JavaScript file for server-based data processing and integration. Text-based flow representations can be exchanged between instances. If a node used in one implementation of Node-RED is not usable anywhere else, a temporary node is placed to ensure the user implements the missing node before flow deployment in the UI.

### MQTT Box
MQTT Box is a helper program to develop and load test MQTT based clients, brokers, devices, cloud and apps. Every aspect of MQTT Box is specifically designed to maximize development and testing productivity. Together, with MQTT clients and load testing tools integrated, it's powerful enough to supercharge your MQTT workflow. MQTT Box provides support on Windows, Linux, Chrome, Mac and Web. It also provides ‘subscribe/publish’ functionality along with support for important protocols like 6LoWPAN WSN. Combined with an aesthetically pleasing and simple interface, MQTT Box is the primary broker software for any IoT application.

### IFTTT
IFTTT derives its name from the programming conditional statement “if this, then that” and it helps all your apps and devices work better together. On IFTTT we can create applets. 

## Hardware Used
1. DHT 11 Module (Temperature and Humidity sensor)
2. NodeMCU ESP8266 Module (Microcontroller)
3. Breadboard
4. Connecting wires ( F-F)

## Circuit Connection
![connection](https://user-images.githubusercontent.com/62541787/127278142-8f7c7bc9-6601-497c-b2bf-dda82258e24e.PNG)
![practical_connection](https://user-images.githubusercontent.com/62541787/127278315-8d677ba6-ce72-401a-9954-97a9f5e04da5.jpg)




