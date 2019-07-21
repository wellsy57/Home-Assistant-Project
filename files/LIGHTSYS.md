# Lighting Control, Movement Sensors and Area Occupation

[MOVEMENT](https://github.com/wellsy57/Home-Assistant-Project/blob/master/files/MOVEMENT.md) | 
[MODBUS](https://github.com/wellsy57/Home-Assistant-Project/blob/master/filyes/MODBUS.md) | [MQTT](https://github.com/wellsy57/Home-Assistant-Project/blob/master/files/MQTT.md)

Automated Lighting control for outside areas has been in place via my Modbus PLC'S using PIR Sensors, local wall switches, light relay and 'occupied/unoccupied entity' for a fair while. I have a newer system in my rumpus room which is based on sonoff basics performing the functions of local wall switches, light relay, PIR sensors and the 'occupied/unoccupied entity.  

Using a system based on 'occupation' is working out very well. I have plans to progress rolling this out through the rest of the house as time permits.

Lighting can turned on or off anytime by local switches. Movement (PIR sensors often several within the area) will trigger an 'occupied' status once detected. The 'occupied' state remains active for a set interval of time unless more movement is detected. once the 'occupied' state is changed to 'unoccupied' an automation turns off all lights within the area unless the system is in 'manual mode'.

Auto mode uses a daylight switch which changes state at sunset (or overcast conditions) which causes an area becoming 'occupied' to trigger an automation to turn on the required lights. Lights remain on until the room becomes 'unoccupied'.


[Back to Readme](https://github.com/wellsy57/Home-Assistant-Project/blob/master/README.md)
