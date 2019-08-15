# Lighting Control, PIR Sensors and Occupation

[HOME] | [MOVEMENT](https://github.com/wellsy57/Home-Assistant-Project/blob/master/files/MOVEMENT.md) | 
[MODBUS](https://github.com/wellsy57/Home-Assistant-Project/blob/master/files/MODBUS.md) | [MQTT](https://github.com/wellsy57/Home-Assistant-Project/blob/master/files/MQTT.md) | [README](https://github.com/wellsy57/Home-Assistant-Project/blob/master/README.md)

## Modbus + HA

Automated lighting control for outside areas has been in place via my Modbus PLC'S using PIR Sensors, local wall switches, light relays and the 'occupied entity' for a fair while. All sensors and wall switches used on the PLC system are wired to digital inputs on the PLC. The Function Block Diagram (FBD) Program on the PLC provides ALL control logic. To monitor and control the PLC I use a wired ethernet connection to Home-Assistant. This ensures a very robust system. The PLC program is very reliable and as long as there is 24VDC which is fed from a UPS PROTECTED SUPPLY. The PLC program is designed to be aware of the status of 240VAC to power the lights. The system is also wired to ensure local switches are working normally if remote control should fail. 

Remote control fails if my router and/or HA server should fail however these systems are also on a UPS PROTECTED SUPPLY.

## MQTT + WIFI + HA

I have a newer lighting system (which is still evolving) in my rumpus room which is based on sonoff basics performing the functions of local wall switches, light relays, PIR sensors and the 'occupied entity. To ensure reliability, I use a wired switch to the sonoff acting as the light relay of selected lights. As long as there is 240v power, then selected lights continue to work locally. 

For automation I use various Tasmota Rules residing on the applicable sonoff basic's. This provides ALL control logic with communications between devices relying on MQTT and WIFI. Remote control also fails without MQTT, WIFI and HA server however these systems are also on a UPS PROTECTED SUPPLY.

## Auto with local control and occupation

Using an automation system based on 'occupation' is working out very well for me. I have plans to progress rolling this out throughout the rest of the house as time permits.

Lighting can be turned on or off anytime by local switches. Movement (PIR sensors often several within the area) will trigger an 'occupied' status once detected. The 'occupied' state remains active for a set interval of time unless more movement is detected.  

Further movement detection always resets the time interval. Once there is no further movement and the 'occupied' state is changed to 'unoccupied' an automation turns off all lights within the area.

Automation also uses a daylight sensor which constantly monitors light levels. The state of the daylight sensor changes around sunset or during overcast conditions which causes an area also becoming 'occupied' to trigger an automation to turn on the required lights. Lights remain on until the room becomes 'unoccupied' OR are turned off manually. At sunrise or when overcast conditions clear lights will not be triggered.


[Back to Readme](https://github.com/wellsy57/Home-Assistant-Project/blob/master/README.md)
