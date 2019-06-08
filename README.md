# TempHumSensor
This repository is about making my simple temprature and humidity sensor which connects via MQTT. 

## Parts 
- Wemos D1 Mini
- Sensor SHT30
- USB Adapter
- Micro USB Cable 

## Hardware preparation
- Solder the [Wemos D1 Mini](https://wiki.wemos.cc/products:d1:d1_mini)
- Solder [SHT30](https://wiki.wemos.cc/products:d1_mini_shields:sht30_shield)
- Click this shield on the Wemos
- Plug the USB Cable in your computer

## Software preparation
- Flash your Wemos with [Tasmota firmware](https://github.com/arendst/Sonoff-Tasmota/wiki/Flashing)
- After flashing pull the Wemos out of your computer and back in. 
- In your WIFI network will show up a new not secured network with the name "sonoff-XXXX". This number is not fixed. 
- Connect with this network
- After connection an authentication module will popup, otherwise browse to: 192.168.4.1 or check with a portscanner with IPadres is alive. 
- In this authentication module you'll need to enter your network credentials. _You don't need to give 2 SSID, one is enough and remember this Wemos only supports 2.4Ghz network_.
- Now search for this the Wemos in your network.
- Browse to it's IPadres 
- General Configuration
    - Click on Configuration > Configuration Other 
    - Check if MQTT is enabled. 
    - Enter a friendly name. 
    - Click on 'save' 
    - The Wemos will restart.
- Configuration of MQTT 
    - Click on Configuration > Configuration MQTT
    - Enter MQTT server
    - Enter MQTT port
    - Enter a name for client
    - Enter a username (you can leave the password blank, later you can change this)
    - Enter a topic
- Configuration of the board: 
    - Click on Configuration > Configuration Module 
    - Choose Module Type Generic(18)
    - Click on 'save', the GUI will change the layout to this module type.
    - Click on Configuration > Configuration Module
    - Choose for **D2 GPIO4 : I2C SDA**
    - Choose for **D1 GPIO5 : I2C SCL**
    - Click on 'save' 
- After rebooting in the main menu there will show up:
    - _SHT3X-0x45 Temperature	25.5°C_
      _SHT3X-0x45 Humidity	    52.0%_
- Go to console to check the topic which you can read from your MQTT broker

## Design prepration
- Check STL files in this repository 
- Print this case with a 3D printer 
 
Specs: 
- Length: 6 cm
- Width: 3.5 cm
- Heigth: 3 cm 
