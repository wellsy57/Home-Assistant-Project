[LIGHTING](https://community.home-assistant.io/t/lighting-control-pir-sensors-and-occupation/131955) | [IRRIGATION](https://community.home-assistant.io/t/irrigation-and-misting/133716) | INPUT |  [TREATMENT](https://community.home-assistant.io/t/treatment-processes/132729) | [FILTRATION](https://community.home-assistant.io/t/filtration-streams/133086) | [SOLIDS](https://community.home-assistant.io/t/solids-filtrate-recovery/133450) | [PLC](https://community.home-assistant.io/t/plc-programming/133839) | [myHome-Assistant Project](https://community.home-assistant.io/t/myhome-assistant-project/131756)

Input to the Storage and Treatment Systems comes from several areas outside the system but also as return streams within the system.
* **DIRECT RAIN HARVESTING** All areas of the main house roof which can be directly captured in gutters and diverted to the 22,500L main storage tank have been. Remaining main house roof areas run to the street for now with future plans to capture and transfer to the tank. The separate double garage/workshop roof is 100% captured in gutters and diverted to the 55,000L fish pond. The top 200mm of the pond is used as a buffer storage for short term storage and treatment purposes.
* **INDIRECT RAIN HARVESTING** I have installed a substantial stormwater piping system which is designed to capture and direct all rain which falls to ground within my house block and direct it to my storm water sump. An automated pump then transfers that water to my grey water sump which in turn automatically transfers the water to be treated by the treatment system.
* **IRRIGATION, WASHDOWN RUNNOFF HARVESTING** My shadehouse, garden areas and concrete areas have been designed to drain into my stormwater system which is directed to the Storm Water to be sent to be retreated.
* **GREY WATER HARVESTING** I intercept grey water from my bathroom and laundry to be treated. Any excess which cannot be handled by treatment (or if power or system fails) flows to sewer as originally intended.
* **SOLIDS REMOVAL FILTRATE HARVESTING** Treatment and filtration produces a high nutrient solids waste which is filtered and the solid matter is removed to a compost heaps for later garden and lawn use OR pumped to sewer if not able to handle the quantity produced. Filtrate is then retreated.

There are three Input Sumps designed to contain and then control the further progress of any input streams entering the system or those being returned for further treatment.

## Grey Water Sump

The Grey Water Sump is installed adjacent the bathroom and laundry to allow both these grey water streams to be harvested and then be pumped to the treatment system. 

![GreyWaterSump|571x499](upload://dBIcUsTWnhyvFq6LYcKBfOOXY0f.jpeg) 

The sump is fitted with a sump pump, non-return valve and high/low level sensors which have proven themselves to be 100% reliable given adequate maintenance. Maintenance requires a regular disassembly and reassembly of the non-return valve to ensure 100% reliability and then visual inspection of the sump pump, pressure switches, tubing, mounting fittings etc. I then check for any debris buildup and carry out a thorough cleaning of all sump equipment if required. I also test operation is at the required liquid levels and is reported correctly to Home-Assistant.

The pump is a 25mm discharge, Davey dirty water type stainless steel pump.

![D15VA_500x_crop_center|500x500](upload://w2jDpew2MQfhS1fHyVNY7lvDgRz.jpeg) 

The sensor type is the same type as pressure switches used in clothes washing machines and dish washers for level control. 

![PressureSwitch|544x500](upload://33rgsDsxer8gIITwwOGRILsD210.jpeg) 

I have designed my own bubble trap to be be more robust and have easier adjustment means to allow accurate level control from a mounting point easily accessible at the top of the sump.

![GreyWaterSumpBubbleTrap|546x500](upload://ip0AMzT2OOQogaUndAKgbRozKPd.jpeg) 

The pumped output from the sump is dependent on the readiness of the treatment system to treat the stream. Readiness is based on the Anoxic Tank being below high level AND the number of times the Grey Water Sump Pump has run in the past 6 hours must also be less than the current pumping setpoint. High level pauses the pump while reaching the setpoint trips the pump until it is reset after 6 hours elapses.

Any failure of upstream equipment, power outage, or control systems failure will cause the sump to refuse further return input being pumped. Should there be any shower use, hand basin use or washing machine discharge the sump liquid level will rise above the sewer return pipe level which ensures nothing ever overspills the sump but simply runs freely to the sewer.

## Storm Water Sump

The Storm Water Sump is connected to both the Rain Water Storage overflow pipe and the lowest level of all the upper level Storm Water piping.

![StormwaterSump02|375x500](upload://3FxFyDZfMZy90Ep7JxDlD5EmgB4.jpeg) 

The sump is fitted with an output coarse screen, sump pump and high/low level sensors which have proven themselves to be 100% reliable given adequate maintenance. Maintenance simply requires a regular visual inspection of the sump pump, pressure switches, tubing, mounting fittings etc. I also check for any debris buildup and carry out a thorough cleaning of the output coarse screen and all sump equipment if required. I also test operation is at the required liquid levels and is reported correctly to Home-Assistant.

![StormwaterSump|504x499](upload://yOTXQxYWxLsm0OMM5LldqxK1LrN.jpeg) 

The pump is a 1500L/hour pond pump. The sensor type is the same type as pressure switches used in clothes washing machines and dish washers for level control. I have designed my own bubble trap to be be more robust and have easier adjustment means to allow accurate level control from a mounting point easily accessible to one side of the sump.

The pumped output from the sump is dependent on the readiness of the grey water system to accept the stream. Readiness is based on the Grey Water Sump being below high level.

# Garage Sump

The Garage Sump is connected to the upper storm water pipework adjacent the Garage Doorway.

The sump is fitted with a sump pump and a low level sensor which have proven themselves to be 100% reliable given adequate maintenance. Maintenance simply requires a regular visual inspection of the sump pump, pressure switch, tubing, mounting fittings etc. I also check for any debris buildup and carry out a thorough cleaning of all sump equipment if required. I also test operation is at the required liquid levels and is reported correctly to Home-Assistant.

The pump is a 1000L/hour pond pump. The sensor type is the same type as pressure switches used in clothes washing machines and dish washers for level control. I have designed my own bubble trap to be be more robust and have easier adjustment means to allow accurate level control from a mounting point easily accessible at the top of the sump.

The pumped output from the sump is independent of other levels or system readiness as this pump only collects stormwater or irrigation overflow which if left insitu will find its way inside the garage as it's level rises. As the sump is only equipped with a low level sensor the operation is set to begin after a timed period upon first sensing low level.

# HA screenshot

![INPUTscreenshotEdit|690x386](upload://z60LMhPtIP5KmRISyWkgVEBNuyE.png) 


[myHome-Assistant Project](https://community.home-assistant.io/t/myhome-assistant-project/131756)
