# Lighting Control, PIR Sensors and Occupation

[MOVEMENT](https://github.com/wellsy57/Home-Assistant-Project/blob/master/files/MOVEMENT.md) | 
[MODBUS](https://github.com/wellsy57/Home-Assistant-Project/blob/master/files/MODBUS.md) | [MQTT](https://github.com/wellsy57/Home-Assistant-Project/blob/master/files/MQTT.md)

## Modbus + HA

Automated Lighting control for outside areas has been in place via my Modbus PLC'S using PIR Sensors, local wall switches, light relay and 'occupied/unoccupied entity' for a fair while. All sensors, wall switches, etc on the PLC system are wired to digital inputs. The Function Block Diagram (FBD) Program on the PLC provides ALL control logic. To monitor and control the PLC I use TCP Ethernet connections to Home-Assistant. This is a very robust system. The PLC program is 98% reliable as long as there is 24VDC (fed from a UPS PROTECTED SUPPLY) for the PLC and 240VAC to power the lights. The system is wired to ensure local switches are working as expected if remote control should fail. 

Remote control fails if my router and/or HA server should fail however these systems are on a UPS PROTECTED SUPPLY.

## MQTT + WIFI + HA
I have a newer lighting system in my rumpus room which is based on sonoff basics performing the functions of local wall switches, light relay, PIR sensors and the 'occupied/unoccupied entity. To ensure reliability, I use a wired switch to the sonoff acting as the light relay. As long as there is 240v power, lights work locally. 

For Automation I use various Tasmota Rules residing on the applicable sonoff basic's. This provides ALL control logic with communications between devices relying on MQTT and WIFI. Remote control also fails without MQTT, WIFI and HA server however these systems are on a UPS PROTECTED SUPPLY.

## Auto/manual with local control and occupation

Using an automation system based on 'occupation' is working out very well for me. I have plans to progress rolling this out throughout the rest of the house as time permits.

Lighting can turned on or off anytime by local switches. Movement (PIR sensors often several within the area) will trigger an 'occupied' status once detected. The 'occupied' state remains active for a set interval of time unless more movement is detected.  

Movement always resets the time interval. Once there is no further movement and the 'occupied' state is changed to 'unoccupied' an automation turns off all lights within the area unless the system is in 'manual mode'.

Auto mode uses a daylight switch which changes state at sunset (or during overcast conditions) which causes an area also becoming 'occupied' to trigger an automation to turn on the required lights. Lights remain on until the room becomes 'unoccupied' OR are turned off manually.


[Back to Readme](https://github.com/wellsy57/Home-Assistant-Project/blob/master/README.md)
