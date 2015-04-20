# monkey-medsensor
The Monkey MedSensor project by the Men in Yellow Hats

This is the submission by Team Men in Yellow Hats for the UMKC Spring 2015 Hackathon

Our team consists of Adam Carter, Mike Rzepka, Jim Dowling, and Lakshmana Dheeraj Polisetty.

Our project is the Monkey MedSensor.

A Link to our Demo Video can be found here:  http://youtu.be/ANedFNE19qU.

Slides for our Presentation can be found under the main folder for this repository.

#Components
Our system was built using three primary components:
- A Java-based MQTT Messaging Device that transmits some basic vital stat information (heart rate, blood pressure, temperature, and O2 Saturation %) once per second.
- A Node-Red based Internet of Things service using MongoDB for data storage and REST calls for data access
- A Client Site developed in HTML5 using JavaScript, jQuery, Bootstrap, and Google Chart API to present the data

#Device Simulator
Our Device Simulator uses the Paho MQTT library to communicate with the Internet of Things service.  We created 10 device footprints, and we transmit our data once per second.  While most of the values will transmit as viewed in the application, we added a heart rate margin of fluctuation so that it randomly picks a value within 3 of the actual value selected so we can simulate some randomness in our data.

Code for this device can be found in the src/mqtt-device-test project folder.

#Node-Red
Our Device Simulators all feed into our Node-Red configuration, which filters the messages as they arrive.  The latest message is pared down and sent to our live collection.  Once every 60 seconds, we write out a historical row to maintain history.  Also, a remove message is supported to remove a patient from the live table when their device shuts down.

We added additional REST endpoints to provide access to our live and historical data.

The JSON export of the Node-Red configuration can be found under src/Node-Red

#Client
Our client site provides a real-time view of the live data, continually updating to ensure the live data is present.  The user has options from there to view the historical data for one of these patients.  This will present them with broken down charts for each major vital statistic.

Code for this site can be found under src/Monkey MedSensor.




