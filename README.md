Built Your Own GPS Tracker with Geofence Using Xiao ESP32-S3

This project demonstrates how to build a low-cost GPS tracker with geofencing and SMS alerts using the Seeed Studio XIAO ESP32-S3 and the NEO-6M GPS module.Unlike traditional GPS trackers that require GSM modules and SIM cards, this project uses Wi-Fi to transmit the device’s real-time GPS location to GeoLinker Cloud-a free service by Circuit Digest.Using GeoLinker, you can view real-time location points, route history, and receive SMS alerts when the device exits the geofence boundary.

🛰️ Features:
•	📡 Real-time GPS tracking
•	🗺️ Route history plotted automatically
•	🚧 Geofence support (custom radius)
•	📩 SMS alerts on geofence breach
•	📶 Works on Wi-Fi no SIM card or GSM module needed
•	💾 Offline data storage when internet fails
•	🔁 Automatic sync to cloud when connection returns
•	🆓 Completely free to use with GeoLinker Cloud

🔧 Components Required:

Hardware:
•	1 × XIAO ESP32-S3
•	1 × NEO-6M GPS Module
•	1 × External GPS Patch Antenna
•	1 × Breadboard
•	Jumper wires
Software:
•	Arduino IDE




🖧 System Workflow

The ESP32-S3 reads latitude & longitude from the NEO-6M GPS module.GPS data is uploaded to GeoLinker Cloud through Wi-Fi.If the device crosses the preset geofence radius, an SMS alert is triggered.If internet disconnects, data is stored locally and synced once Wi-Fi is back.All locations are visible as plotted points with full route history.

🔌 Circuit Diagram

Connection Overview:

NEO-6M VCC → 5V (XIAO ESP32-S3)
NEO-6M GND → GND (XIAO ESP32-S3)
NEO-6M TX → ESP32-S3 RX
NEO-6M RX → ESP32-S3 TX
GPS patch antenna → NEO-6M antenna port

This ensures stable GPS communication and proper serial data flow.

🌐 GeoLinker Setup (API Key + SMS Access)

•	Visit CircuitDigest.cloud
•	Create or log in to your account
•	Go to My Account → Generate API Key
•	Copy the API key
•	Link your mobile number to enable SMS alerts

API limits:
100 SMS messages per API key
10,000 GPS data points

🧠 Code Overview
•	The code performs:
•	GPS decoding using TinyGPS++
•	Secure HTTPS communication
•	Data uploading to GeoLinker via GeoLinker library
•	Geofence distance calculation using Haversine Formula
•	SMS triggering on geofence breach
•	Offline buffering during network failure
📂 Source Code (main highlights)
GPS pins: RX = 44, TX = 43, Baud = 9600
Update interval = 15 seconds
Geofence center coordinates are predefined in the code
sendSMS() sends location alerts via API

▶️ Working

•	Power the ESP32-S3 through USB
•	Connect your mobile hotspot or Wi-FiWhen tracking begins, GeoLinker shows live location updates.
•	If the device exits the geofence radius SMS is sent with coordinates
•	When Wi-Fi disconnects data is saved locally and uploaded once Wi-Fi returns
•	During movement, GeoLinker draws the route on the map

Project link
https://circuitdigest.com/microcontroller-projects/gps-tracker-with-seeed-studio-xiao-esp32-s3-and-geofencing


🏁 Conclusion

This project demonstrates a reliable, low-cost GPS tracking solution using the XIAO ESP32-S3 and NEO-6M GPS module.Geofencing, SMS alerts, Wi-Fi tracking, and offline buffering make it practical for many real-world applications.
Author:
Vedhathiri.K

