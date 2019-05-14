# Home-Assistant Project

## This is a place to document my progress with moving from mySCADA to Home-Assistant the aim being to provide for a more reliable means of local, remote control and monitoring of my existing home systems

## Background

Several decades ago I started automating the watering of my shadehouse for my hobby of growing Australian native plants (including orchids). I was using very simple 12volt relay logic and some modified 240V programmable timers and valves controlled by modified car windscreen wiper motors. My system had only very basic local control. At that time we lived in a remote location with no mains power. Our only means of 'always on' power being an 84W 12V solar array with 1000 amp/hour battery storage.

Leaving the bush for our new home in the city things progressed to start utilizing [Eaton Mini PLC's](https://www.eaton.com/SEAsia/ProductsSolutions/Electrical/ProductsServices/AutomationControl/Automation/ModularProgrammableLogicControllers/index.htm)  with a simple LED Mimic Panel which I divised to allow an operator (the wife or kids) to diagnose system status and faults for me usually in conjunction with phone calls at night.

Later I moved on to [Rievtech PLC's](https://www.rievtech.com) which were purchased from the wonderful Australian supplier Thomas Siegmeth who can be contacted [here](http://www.xlogic.com.au/)

These PLC's were equipped with with [Ethernet connectivity](https://en.wikipedia.org/wiki/Ethernet) using the [Modbus Protocol](https://en.wikipedia.org/wiki/Modbus) to enable a [Scada system](https://en.wikipedia.org/wiki/SCADA) to be developed allowing both local and remote control using various devices including PC's, Mobile Phones, Tablets, etc. Anything with a web browser and local network or internet connection in fact.

I chose an emerging but quite impressive product called [myScada](https://www.myscada.org/en/) to build my Scada Project. When I first started the product was at Version 4. Initially myScada was an emerging system which was still in beta development and they offered a 'free for personal use' unlimited 'tags' and PLC connections. As time went by they also developed iOS and Android apps which in the early days were quite good and relatively bug free. Surprisingly they also included quite good technical help for free.

Unfortunately mySCADA changed to become a very expensive platform with the arrival of version 7. They no longer had a useful free version but as I had become a satisfied user I chose to pay for a 500 tag unlimited PLC connection version. The [mySCADA product is now up to Version 8](https://www.myscada.org/news/).

To be blunt that was possibly the worst mistake I have ever made. However I persisted through several years of bug ridden beta updates with mostly zero help hoping they would get better until I realized I might be able to make a new start with the wonderfull Open Source [Home-Assistant](https://www.home-assistant.io/) product.

# Existing home systems

| Master PLC - Garage Area    | Slave PLC - Shadehouse Area       | House PLC - Meter Box Area | QNAP NAS - Rumpus Area   | Sonoff, Wemos and ESP01 Devices | Cameras   |
|:---------------------------:|:---------------------------------:|:--------------------------:|:------------------------:|:-------------------------------:|:---------:|
|Expansions: 4 Tags: ?        |Expansions: 5 Tags: ?              |Solar Power kWh             |Docker Images: 4          |Devices: 28                      |IP: 1      |
|Grey Water Input             |Activated Sludge Treatment Process |House Power kWh             |home-assistant:0.92.0     |sonoff Basic                     |ESP32: 3   |
|Stormwater Input             |Treatment Tank Levels              |Garage Power kWh            |grafana                   |sonoff 4 Channel:                |Doorbell: 1|
|Rainwater Tank Level         |Pool/Pond Level                    |Cumulative Power kWh        |qiot-mosquitto_amd64:0.1  |wemos D1 Mini: 1                 |Analogue: 6|
|Garage Sump Input            |Reed Bed Level                     |Front Lights                |node-red-docker:0.19.4-v8 |ESP 01: 3                        |DVR: 1     |
|Lower Pond Circulation       |Filtration Tank Levels             |Laundry Path Lights         |                          |Devices: 28                      |           |
|Lower Pond Discharge         |UV Treatment                       |Hot Water Tariff on/off     |                          |Devices: 28                      |           |
|Pressure Pump Control        |Waste (WAS) Management             |Meter Box Voltage Sensors   |                          |Devices: 28                      |           |
|Cooling Fan                  |Fertilizer Level                   |Hot Water Temperature       |                          |Devices: 28                      |           |
|Topup Pond                   |Filtration Flush Control           |                            |                          |Devices: 28                      |           |
|Garage and Outside Lights    |Shadehouse Temperature/Humidity    |                            |                          |Devices: 28                      |           |
|Movement Sensors             |Treated Water Quality              |                            |                          |Devices: 28                      |           |
|Irrigation System            |                                   |                            |                          |Devices: 28                      |           |
|Rainwater Measurement        |                                   |                            |                          |Devices: 28                      |           |
|Mist System                  |                                   |                            |                          |Devices: 28                      |           |
|Pump Area Screen Charger     |                                   |                            |                          |Devices: 28                      |           |
|Garage Area iPad Charger     |                                   |                            |                          |Devices: 28                      |           |
|Garage Roller Door Controller|                                   |                            |                          |Devices: 28                      |           |
|Garage Side Door Open/Close  |                                   |                            |                          |Devices: 28                      |           |
