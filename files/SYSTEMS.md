# Existing home systems and equipment

## Residing on Modbus PLC's under myScada

|Master PLC - Garage Area           |Slave PLC - Shadehouse Area        |House PLC - Meter Box Area         |
|:----------------------------------|:----------------------------------|:----------------------------------|
|Expansions: 4                      |Expansions: 5                      |Expansions: 3                      |
|                                   |                                   |                                   |
|**Functions:**                      |**Functions:**                      |**Functions:**                   |
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
|Rainwater Measurement              |Bio to Slow Sand Filter Pump       |Rumpus Temperature/Humidity        |
|Mist System                        |                                   |Lounge Temperature/Humidity        |
|Pump Area Screen Charger           |                                   |                                   |
|Garage Area iPad Charger           |                                   |                                   |
|Garage Roller Door Controller      |                                   |                                   |
|Garage Side Door Open/Close        |                                   |                                   |
|Garage Control Cabinet Temperature |                                   |                                   |

## Existing equipment running on Home-Assistant

|QNAP NAS - Rumpus Area             |[Sonoff, Wemos and ESP01 Devices](https://github.com/wellsy57/Home-Assistant-Project/blob/master/files/MQTT.md)    |Cameras                            |
|:----------------------------------|:----------------------------------|:----------------------------------|
|Docker Images: 4                   |Devices (Total): 28                |IP Cam: 1                          |
|home-assistant: 0.92.0             |Sonoff Basic: 24                   |ESP32: 3                           |
|grafana                            |Sonoff 4 Channel: 3                |Doorbell: 1                        |
|qiot-mosquitto_amd64:0.1           |wemos D1 Mini: 1                   |Analogue: 6                        |
|node-red-docker:0.19.4-v8          |ESP 01: 3                          |DVR: 1                             |