# Home-Assistant Project

This is a place for me to document my home automation systems and processes.

I will also give a brief outline of my progress with moving from mySCADA to Home-Assistant.
This move has become a necessity to provide me with a more reliable means of local and remote control and monitoring of my existing (and future) home systems.

[HOME](https://github.com/wellsy57/Home-Assistant-Project/blob/master/files/LIGHTSYS.md) | [ENERGY](https://github.com/wellsy57/Home-Assistant-Project/blob/master/files/ENERGY.md) | [TREATMENT](https://github.com/wellsy57/Home-Assistant-Project/blob/master/files/TREATMENT.md)




## Background

I'm an Electrical Fitter/Mechanic with a wide range of experience but a leaning towards automation and control. My own personal journey into automation began when I lived in a remote location in north Queensland with no access to mains power. Our only means of 'always on' power being an 84W 12VDC solar array with 1000 amp/hour battery storage.

I started automating the watering and misting of my shadehouse for my hobby of growing Australian native plants (including orchids). I developed a system using 12VDC relays and some modified 240VAC programmable timers. The now 12VDC timers and relays controlled valves actuated by modified 12V car windscreen wiper motors. 

Times changed and we left the bush for a suburban home south of Brisbane. After constructing a new shadehouse things quickly progressed to a more refined 24VAC programmable timer system using 24VAC relays and 24VAC solenoids. Later I began utilizing a couple of [Eaton Mini PLC's](https://www.eaton.com/SEAsia/ProductsSolutions/Electrical/ProductsServices/AutomationControl/Automation/ModularProgrammableLogicControllers/index.htm) to build my own custom irrigation and misting controller with precise misting control down to seconds. This system was equipped with a simple LED Mimic Panel which I divised to allow an operator (the wife or kids) to diagnose system status and any faults for me usually in conjunction with phone calls at night due to me working away.

Later I moved on to higher spec [Rievtech PLC's.](https://www.rievtech.com) My system was expanding beyond irrigation, misting and storage to include water treatment and solar power monitoring and outside lighting control so I considered that I needed remote monitoring and control capability. 


I chose the Rievetech PLC's because they were equipped with with [Ethernet connectivity](https://en.wikipedia.org/wiki/Ethernet) using the [Modbus Protocol](https://en.wikipedia.org/wiki/Modbus) so I was now able to include a [Scada system](https://en.wikipedia.org/wiki/SCADA) with local and remote control by various devices including PC's, Mobile Phones, Tablets, etc. You could use anything with a web browser and local network or internet access in fact. Programming of the PLC's is done using easy to learn xLogic Soft Function Block Diagram Software which is a [free download from here.](https://www.rievtech.com/download.html) You can also download Manuals, regular PLC updates and a bunch of other useful items as well.

## But why PLC'S?

Because PLC's operate autonomously on the near-real time control of the process, using the last command given from the supervisory system. Failure of the communications network does not necessarily stop the plant process controls, and on resumption of communications, the operator can continue with monitoring and control. If all sensors, switches, instruments, etc are hard wired to the PLC and the program is carefully designed any unsafe outcomes will halt the process with no user intervention required. Operators can always use local control stations (LCS) to halt any unsafe equipment operation.

## Scada

The Scada product I chose was [myScada](https://www.myscada.org/en/). When I first started using the product it was at Version 4 and was still in beta development. As such the makers offered a free for personal use, unlimited tags and PLC connections product which was fantastic. As time went by they also developed very affordable iOS and Android apps which in the early days were quite good and relatively bug free. Surprisingly they also included quite good technical help for free.

Unfortunately mySCADA changed to become a very expensive (and very buggy) platform with the arrival of Version 7. They no longer offered a useful free to use version but as I had become a satisfied user I chose to pay for a 500 tag, unlimited PLC connection version to accommodate my project which had well over 300 tags and 4 PLC's. They now offered a paid tech support service for 'premium support' and a free tech support service 'without any real support' unfortunately. The final straw for me was when Version 8 arrived and I wanted to shift my software to new server I received zero help with a new Product Key which was required on the new server.

So the search began for a better solution which ended up being Home-Assistant.

## Home-Assistant

I purchased a Raspberry PI 3b+ and setup some Sonoff Basic switches flashed with Tasmota and quickly realized how powerful HA was. What really thrilled me was the incredible wealth of community help for seemingly every problem that arose.

My only concern was how long it took to reboot the PI. I could literally go and make a cup of coffee every time a restart was required. After some more research I realised that HA could also be installed on a higher spec machine as well.

It was after installing [Home-Assistant](https://www.home-assistant.io/) on a [QNAP TS-453 Pro NAS](https://www.qnap.com/en-au/product/ts-453%20pro) that I realized I might actually be able to use it as a viable alternative to a buggy, poorly supported and overpriced SCADA product.

As [Home-Assistant natively supports Modbus](https://www.home-assistant.io/components/modbus/) I started with a spare PLC and set it up with a small program with examples of switches, binary sensors and sensors to check that moving would be possible.

This first test worked well however I soon realised there was a [problem with having multiple modbus clients](https://community.home-assistant.io/t/ability-to-add-multiple-modbus-hubs/16365) and as I have four modbus devices requiring four modbus hubs then that was a real problem for me. Luckily for me there was a [workaround](https://community.home-assistant.io/t/multiple-tcp-modbus-slaves/99210/2) which had been [developed by PtP](https://community.home-assistant.io/u/PtP) so I set about testing that with a second PLC and it worked seamlessly. The final two PLC's were also added and I confidently flicked the switch off on the myScada server for good. The best news came when [support for multiple modbus hubs and writing to registers was added to the 0.88.0 release](https://github.com/home-assistant/home-assistant/pull/21238).  

## My Guiding Automation Principles

1. PLC's operate autonomously on the near-real time control of the process, using the last command given from the supervisory system. Failure of the communications network does not necessarily stop the plant process controls, and on resumption of communications, the operator can continue with monitoring and control.

2. Always include local lockout where malfunction of automation or control could cause unsafe conditions.

3. Ensure all equipment is installed and maintained in a safe manner.

4. Never allow remote control or supervisory systems to override local lockout control.


[Modbus](https://www.home-assistant.io/components/modbus/) | [Modbus Binary Sensors](https://www.home-assistant.io/components/binary_sensor.modbus/) | [Modbus Climate](https://www.home-assistant.io/components/climate.modbus/) | [Modbus Sensor](https://www.home-assistant.io/components/sensor.modbus/) | [Modbus Switch](https://www.home-assistant.io/components/switch.modbus/)
