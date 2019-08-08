#  TEXAS Instruments SENSOR TAG and Raspberry PI 3 Model B using Bluetooth Low Energy
	
	
author: Orestis Evangelatos, orestevangel@gmail.com
September 2016
Copyright 2016 Orestis Evangelatos

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.




TEXAS Instruments SENSOR TAG and Raspberry PI 3 Model B using Bluetooth Low Energy
===================================================================================

This is a simple example for the TI SensorTag using RaspberryPi 3.0 Model B which has already embedded a Bluetooth Low Engery (BLE GATT) antenna.

As a first example I have integrated in the python file the collection of data measurements from:
1. IR and Ambient Temperature
2. Luminance
3. Humidity
4. Barometric Pressure

Later the following were added by Jamal on August 2019 
5. Movement sensor (this includes Gyroscope,Accelerometer,Magnetometer)
6. Python code example to send data to Azure cloud

In the website of Texas Instruments you can find more information on the details of the other sensors. The logic is the same; you should at first
enable the sensor using the appropriate value for the appropriate register and then read the output from the appropriate register. 
The website of sensor tag is:  
http://www.ti.com/tool/TIDC-CC2650STK-SENSORTAG 
and this: http://processors.wiki.ti.com/index.php/CC2650_SensorTag_User’s_Guide


**************Instructions***************
Have a look into this youtube short instruction: https://youtu.be/jLnmJ3L9Ahg

If your Raspberry Pi 3 has no bluetooth communication stack installed then you need to install Bluez first. Take help from this link:
    https://developer.ibm.com/recipes/tutorials/ti-sensor-tag-and-raspberry-pi/

Before you start you will need to install the python pexpect libray using the following command:
    sudo pip install pexpect

To enable the bluetooth adaptor and find your SensorTag device address do the following -
    sudo hciconfig hci0 up
    sudo hcitool lescan 

Press the side button and you should get a couple of lines showing the device is working. 
You should see something like this: 
    B0:B4:48:C8:41:81 CC2650 SensorTag

Note down the MAC address of your SensorTag device. Now go to the script [sensortag.py] and insert the MAC address of your SensorTag in line 215:    
    bluetooth_adr = "your-SensorTag-MAC address"

Hit Ctrl-C to exit.  Now you're ready to go -
    python sensortag.py
    
    
# Have fun!
 Orestis
