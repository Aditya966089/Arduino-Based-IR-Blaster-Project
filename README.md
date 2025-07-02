# Arduino-Based-IR-Blaster-Project

**Implementation of Project**  
*IR Reception:* In the project, we have to  capture the infrared signal of the desired device whose remote we want to make. For that we use the TSOP which is basically an Infrared capturing device. We use the IR remote library in the Arduino IDE and upload the Receiving code as written in the receiving code folder, which decodes the IR signal received from the remote.   
IR Transmission: Next we have to transmit the signal through the IR led. We upload the sending code as written there.   
WiFi Integration: Then we have to integrate the wifi module with the google assistant. For that, we use the IFTTT platform where we integrate google assistant in the ‘If this’ box, and in the ‘then this’ box, we put the ip address of out arduino and wifi module. When the phrase “IR ON” will be said in the google assistant, then it will send a signal to the wifi module through the IP address of the module,and then the module will command the arduino to send the desired particular code of the device to be operated. In this way, we can implement the project.

**File Names**  
*Source Code:* This folder contains three codes in which the first code is for receiving the ir signal and to decode it. We copy and paste the decoded code somewhere and store it. The second code is for sending the IR signal where we send the IR code we want to send manually. Now to control it through the google assistant, we upload the wifi connection code and then through the integration of google assistant with the wifi module through thingspeak, we can control the arduino for sending particular codes.  
*Circuit Diagram:* It contains the circuit diagram of the project that we have made.  
*Output:* It contains the screenshot of output that we got from the receiving code.  
*Snapshots:* In this folder, there are screenshots of setting up google assistant routines for sending command to the wifi module through thingspeak platform and the thingspeak’s api generator page for connection to different devices.

**Installation Steps for Softwares**

1\. Add ESP8266 Support to Arduino IDE

1. Open Arduino IDE.  
2. Go to File \> Preferences.

In the Additional Board Manager URLs field, add this URL:  
 https://arduino.esp8266.com/stable/package\_esp8266com\_index.jso

3. Click OK.  
4. Go to Tools \> Board \> Boards Manager.  
5. Search for "ESP8266" and install the latest version.

---

### 2\. Install Required Libraries

Install the libraries necessary for IR communication and HTTP handling:

1. Open Arduino IDE.  
2. Go to Sketch \> Include Library \> Manage Libraries.  
3. Search for and install the following libraries:  
   * IRremote (for sending and receiving IR signals)  
   * WiFiEsp (for ESP8266 communication in AT command mode)  
   * ArduinoJson (for parsing HTTP responses, optional)

After uploading the wifi connection code we configure the IFTTT  as below:-

3\. Configure IFTTT for Voice Commands

1. Create an account on [IFTTT](https://ifttt.com/).  
2. Create an Applet:  
   * Trigger: Choose Google Assistant and configure a voice command (e.g., "Turn on the TV").  
   * Action: Select Webhooks and configure the HTTP request (method: `GET`, URL: ESP8266 IP).  
3. Save the applet and test it with Google Assistant.

   
