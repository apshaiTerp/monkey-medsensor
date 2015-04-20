# monkey-medsensor
The Monkey MedSensor project by the Men in Yellow Hats

This is the submission by Team Men in Yellow Hats for the UMKC Spring 2015 Hackathon

Our project is the Monkey MedSensor.

#Components
Our system was built using three primary components:
- A Java-based MQTT Messaging Device that transmits some basic vital stat information (heart rate, blood pressure, temperature, and O2 Saturation %) once per second.
- A Node-Red based Internet of Things service using MongoDB for data storage and REST calls for data access
- A Client Site developed in HTML5 using JavaScript, jQuery, Bootstrap, and Google Chart API to present the data

#Device Simulator
Our Device Simulator uses the Paho MQTT library to communicate with the Internet of Things service.  We created 10 device footprints, and we transmit our data once per second.  While most of the values will transmit as viewed in the application, we added a heart rate margin of fluctuation so that it randomly picks a value within 3 of the actual value selected so we can simulate some randomness in our data.

#Node-Red
O