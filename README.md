# Home-Assistant Project

## This is a place to document my progress with moving from mySCADA to Home-Assistant the aim being to provide for a more reliable means of local, remote control and monitoring of my existing home systems

## Background

I'm a licenced Electrical Fitter/Mechanic who often works away on large construction projects.
Several decades ago I started automating the watering of my shadehouse for my hobby of growing Australian native plants (including orchids). I was using very simple 12volt relay logic and some modified 240V (to run on 12V) programmable timers and several valves actuated by modified 12V car windscreen wiper motors. My system had only very basic local control. At that time we lived in a remote location with no mains power. Our only means of 'always on' power being an 84W 12V solar array with 1000 amp/hour battery storage.

Leaving the bush for our new home in the city things quickly progressed to start utilizing [Eaton Mini PLC's](https://www.eaton.com/SEAsia/ProductsSolutions/Electrical/ProductsServices/AutomationControl/Automation/ModularProgrammableLogicControllers/index.htm) with a simple LED Mimic Panel which I divised to allow an inexperienced operator (the wife or kids) to diagnose system status and any faults for me usually in conjunction with phone calls at night due to me working away.

Later I moved on to [Rievtech PLC's](https://www.rievtech.com) which were purchased from the wonderful Australian supplier Thomas Siegmeth who can be contacted [here](http://www.xlogic.com.au/)

These PLC's were equipped with with [Ethernet connectivity](https://en.wikipedia.org/wiki/Ethernet) using the [Modbus Protocol](https://en.wikipedia.org/wiki/Modbus) to enable a [Scada system](https://en.wikipedia.org/wiki/SCADA) to be developed allowing both local and remote control using various devices including PC's, Mobile Phones, Tablets, etc. Anything with a web browser and local network or internet connection in fact.

I chose an emerging but quite impressive product called [myScada](https://www.myscada.org/en/) to build my Scada Project. When I first started the product was at Version 4. Initially myScada was an emerging system which was still in beta development and they offered a 'free for personal use' unlimited 'tags' and PLC connections. As time went by they also developed iOS and Android apps which in the early days were quite good and relatively bug free. Surprisingly they also included quite good technical help for free.

Unfortunately mySCADA changed to become a very expensive (and very buggy) platform with the arrival of Version 7. They no longer offered a useful free to use version but as I had become a satisfied user I chose to pay for a 500 tag unlimited PLC connection version to accommodate my project which had over 300 tags and 4 PLC's. They now offered a paid tech support service for premium support and a free tech support service without any real support unfortunately.

To be blunt that purchase was possibly the worst mistake I have ever made. However I persisted through many bug ridden beta updates with mostly zero help hoping they would get better until I realized I might be able to make a new start with the wonderfull Open Source [Home-Assistant](https://www.home-assistant.io/) product.

## Existing home systems residing on Modbus PLC's under myScada

|Master PLC - Garage Area           |Slave PLC - Shadehouse Area        |House PLC - Meter Box Area         |
|:----------------------------------|:----------------------------------|:----------------------------------|
|Expansions: 4                      |Expansions: 5                      |Expansions: 3                      |
|                                   |                                   |                                   |
|**Functions:**                      |**Functions:**                      |**Functions:**                      |
|Grey Water Input                   |Activated Sludge Treatment Process |Solar Power kWh                    |
|Stormwater Input                   |Treatment Tank Levels              |House Power kWh                    |
|Rainwater Tank Level               |Pool/Pond Level                    |Garage Power kWh                   |
|Garage Sump Input                  |Reed Bed Level                     |Cumulative Power kWh               |
|Lower Pond Circulation             |Filtration Tank Levels             |Front Lights                       |
|Lower Pond Discharge               |UV Treatment                       |Laundry Path Lights                |
|Pressure Pump Control              |Waste (WAS) Management             |Hot Water Tariff on/off            |
|Control Cabinet Cooling            |Fertilizer Level                   |Meter Box Voltage Sensors          |
|Topup Pond                         |Filtration Flush Control           |Hot Water Temperature              |
|Garage and Outside Lights          |Shadehouse Temperature/Humidity    |Movement Sensors                   |
|Movement Sensors                   |Treated Water Quality              |Daylight Switch                    |
|Irrigation System                  |Slow Sand Filter Levels            |Outside Temperature/Humidity       |
|Rainwater Measurement              |Bio to Slow Sand Filter Pump       |Rumpus Temperature/Humidity                                   |
|Mist System                        |                                   |Lounge Temperature/Humidity                                   |
|Pump Area Screen Charger           |                                   |                                   |
|Garage Area iPad Charger           |                                   |                                   |
|Garage Roller Door Controller      |                                   |                                   |
|Garage Side Door Open/Close        |                                   |                                   |
|Garage Control Cabinet Temperature |                                   |                                   |

## Existing equipment running on Home-Assistant

|QNAP NAS - Rumpus Area             |[Sonoff, Wemos and ESP01 Devices](https://github.com/wellsy57/Home-Assistant-Project/Files/MQTT.md)    |Cameras                            |
|:----------------------------------|:----------------------------------|:----------------------------------|
|Docker Images: 4                   |Devices (Total): 28                |IP Cam: 1                          |
|home-assistant: 0.92.0             |Sonoff Basic: 24                   |ESP32: 3                           |
|grafana                            |Sonoff 4 Channel: 3                |Doorbell: 1                        |
|qiot-mosquitto_amd64:0.1           |wemos D1 Mini: 1                   |Analogue: 6                        |
|node-red-docker:0.19.4-v8          |ESP 01: 3                          |DVR: 1                             |