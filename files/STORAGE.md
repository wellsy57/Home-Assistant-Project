# Water Storage and reticulation

STORAGE | 
[IRRIGATION](https://github.com/wellsy57/Home-Assistant-Project/blob/master/files/IRRIGATION.md) | [INPUT](https://github.com/wellsy57/Home-Assistant-Project/blob/master/files/INPUT.md) | 
[TREATMENT](https://github.com/wellsy57/Home-Assistant-Project/blob/master/files/TREATMENT.md) | [FILTRATION](https://github.com/wellsy57/Home-Assistant-Project/blob/master/files/.md) | 
[SOLIDS](https://github.com/wellsy57/Home-Assistant-Project/blob/master/files/SOLIDS.md) | 
[MODBUS](https://github.com/wellsy57/Home-Assistant-Project/blob/master/filyes/MODBUS.md) | [MQTT](https://github.com/wellsy57/Home-Assistant-Project/blob/master/files/MQTT.md) | [README](https://github.com/wellsy57/Home-Assistant-Project/blob/master/README.md)

There are three separate water storage areas to fulfil several needs within the system. 

## Rainwater

First I have a 22,500 litre rainwater/treated water polythene Rainwater Storage Tank. The tank is connected directly to several roof areas for rainwater harvesting and also to the pressure pump reticulation system to allow filling with treated water. A pressure pump is also connected to the rainwater tank discharge to allow water reticulation and water transfer as required.

## Treated Water
Second there are 7 X 200 litre polythene drums (Treated Water Tanks) which are interconnected to give an effective capacity of 900 litres. Another pressure pump is also connected to the treated water tank discharge to allow water reticulation and water transfer as required. 

## Pond
Lastly is a 55000 litre reinforced concrete in-ground swimming pool (the Pond) which has been converted to become a fish pond. This also has a buffer storage capacity of approximately 6000 litres. Water is removed from the pond as required indirectly via redirecting it to a Slow Sand Filter and UV treatment system prior to being stored in the Treated Water Tanks.

## Pressure Pump System

There are two 25mm discharge pressure pumps (in two locations) connected to a common pressure line which runs irrigation solenoids, garden taps and transfer valves within the system. The pumps are controlled via level control and auto or manual control strategies. They are interlocked to ensure only one pump can be in operation at any time.

There is also a connection via a double non-return valve to the mains via a 25mm valve to allow mains water to be used should that be required.

## Irrigation

One of my PLC's is setup to perform Automated Irrigation functions via 25mm 24VAC water control solenoids. 

## Process water

Part of the treatment process requires treated water to flush solids from the process tanks to the Solids Removal tanks. That task is automated by the Treatment PLC via several 25mm 24VAC water control solenoids and a submersible pump.

[Back to Readme](https://github.com/wellsy57/Home-Assistant-Project/blob/master/README.md) | [Readme](https://github.com/wellsy57/Home-Assistant-Project/blob/master/README.md)
