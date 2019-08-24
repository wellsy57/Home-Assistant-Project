# Input

 [STORAGE](https://github.com/wellsy57/Home-Assistant-Project/blob/master/files/STORAGE.md) |
[IRRIGATION](https://github.com/wellsy57/Home-Assistant-Project/blob/master/files/IRRIGATION.md) | INPUT | 
[TREATMENT](https://github.com/wellsy57/Home-Assistant-Project/blob/master/files/TREATMENT.md) | [FILTRATION](https://github.com/wellsy57/Home-Assistant-Project/blob/master/files/FILTRATION.md) | 
[SOLIDS](https://github.com/wellsy57/Home-Assistant-Project/blob/master/files/SOLIDS.md) | 
[MODBUS](https://github.com/wellsy57/Home-Assistant-Project/blob/master/filyes/MODBUS.md) | [MQTT](https://github.com/wellsy57/Home-Assistant-Project/blob/master/files/MQTT.md) | [README](https://github.com/wellsy57/Home-Assistant-Project/blob/master/README.md)

There are three Input Sumps designed to contain and then control the output of any input streams entering the system or those being returned for further treatment.

## Grey Water Sump

The Grey Water Sump is installed adjacent the bathroom and laundry to allow both these grey water streams to be harvested and then be pumped to the treatment system. The sump is fitted with a sump pump and high/low level sensors which have proven themselves to be 100% reliable given adequate maintenance. Maintenance simply requires a regular visual inspection of the sump pump, pressure switches, tubing, mounting fittings etc. I also check for any debris buildup and carry out a thorough cleaning of all sump equipment if required. I also test operation is at the required liquid levels and is reported correctly to Home-Assistant.

The pump is a 25mm discharge, Davey 'dirty water' type stainless steel pump. The sensor type is the same type as pressure switches used in clothes washing machines and dish washers for level control. I have designed my own bubble trap to be be more robust and have easier adjustment means to allow accurate level control from a mounting point easily accessible at the top of the sump. 

The pumped output from the sump is dependent on the readiness of the treatment system to treat the stream. Readiness is based on the Anoxic Tank being below high level AND The number of times the Grey Water Sump Pump has run in the past 6 hours must also be less than the current pumping setpoint. High level pauses the pump while equalling the setpoint trips the pump until it is reset after 6 hours elapses.

Any failure of upstream equipment, power outage, or control systems failure will cause the sump to refuse pumped further input and then on shower use hand basin use or washing machine discharge) the sump liquid level will rise above the sewer return pipe level which ensures nothing ever overspills the sump but simply runs freely to the sewer.

## Storm Water Sump

The Storm Water Sump is connected to both the Rain Water Storage overflow pipe and the lowest level of all the upper level Storm Water piping.

The sump is fitted with a sump pump and high/low level sensors which have proven themselves to be 100% reliable given adequate maintenance. Maintenance simply requires a regular visual inspection of the sump pump, pressure switches, tubing, mounting fittings etc. I also check for any debris buildup and carry out a thorough cleaning of all sump equipment if required. I also test operation is at the required liquid levels and is reported correctly to Home-Assistant.

The pump is a 1500L/hour pond pump. The sensor type is the same type as pressure switches used in clothes washing machines and dish washers for level control. I have designed my own bubble trap to be be more robust and have easier adjustment means to allow accurate level control from a mounting point easily accessible at the top of the sump.

The pumped output from the sump is dependent on the readiness of the grey water system to accept the stream. Readiness is based on the Grey Water Sump being below high level.

# Garage Sump

The Garage Sump is connected to the upper storm water pipework adjacent the Garage Doorway.

The sump is fitted with a sump pump and a low level sensor which have proven themselves to be 100% reliable given adequate maintenance. Maintenance simply requires a regular visual inspection of the sump pump, pressure switch, tubing, mounting fittings etc. I also check for any debris buildup and carry out a thorough cleaning of all sump equipment if required. I also test operation is at the required liquid levels and is reported correctly to Home-Assistant.

The pump is a 1000L/hour pond pump. The sensor type is the same type as pressure switches used in clothes washing machines and dish washers for level control. I have designed my own bubble trap to be be more robust and have easier adjustment means to allow accurate level control from a mounting point easily accessible at the top of the sump.

The pumped output from the sump is independent of other levels or system readiness as this pump only collects stormwater or irrigation overflow which if left insitu will find its way inside the garage as it's level rises. As the sump is only equipped with a low level sensor the operation is set to begin after a timed period upon first sensing low level.


[Readme](https://github.com/wellsy57/Home-Assistant-Project/blob/master/README.md)
