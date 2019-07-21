# Home-Assistant Project

This is a place for me to document my home automation systems and processes.

I will also give a brief outline of my progress with migrating from mySCADA to Home-Assistant.

This move has become a necessity and comes with the aim of being able to provide a more affordable and reliable means of local and remote control and monitoring of my existing home systems.

[HOME](https://github.com/wellsy57/Home-Assistant-Project/blob/master/files/LIGHTSYS.md) | [ENERGY](https://github.com/wellsy57/Home-Assistant-Project/blob/master/files/ENERGY.md) | [TREATMENT](https://github.com/wellsy57/Home-Assistant-Project/blob/master/files/TREATMENT.md)




## Background

I'm a licenced Electrical Fitter/Mechanic with a wide range of experience including working away on large construction projects.
Several decades ago I started automating the watering of my shadehouse for my hobby of growing Australian native plants (including orchids). I developed a very simple system using 12volt relay logic and some modified 240V (to run on 12V) programmable timers. The timers controlled valves actuated by modified 12V car windscreen wiper motors. 

At that time I lived in a remote location in north Queensland with no mains power. Our only means of 'always on' power being an 84W 12V solar array with 1000 amp/hour battery storage.

Times changed and we left the bush for our new suburban home just South of Brisbane. After constructing a new shadehouse things quickly progressed to a more refined programmable timer system and a little later I began utilizing a couple of [Eaton Mini PLC's](https://www.eaton.com/SEAsia/ProductsSolutions/Electrical/ProductsServices/AutomationControl/Automation/ModularProgrammableLogicControllers/index.htm) to build my own custom irrigation and misting controller. This system was equipped with a simple LED Mimic Panel which I divised to allow an operator (the wife or kids) to diagnose system status and any faults for me usually in conjunction with phone calls at night due to me working away.

Later I moved on to higher spec [Rievtech PLC's.](https://www.rievtech.com) My system was expanding to way beyond irrigation, misting and storage to include water treatment and solar power monitoring and a bunch of other systems. The Rievtech PLC's were purchased from the Australian and New Zealand Agent - Thomas Siegmeth who can be contacted [here.](http://www.xlogic.com.au/)

The Rievetech PLC's were equipped with with [Ethernet connectivity](https://en.wikipedia.org/wiki/Ethernet) using the [Modbus Protocol](https://en.wikipedia.org/wiki/Modbus) to enable a [Scada system](https://en.wikipedia.org/wiki/SCADA) to be developed allowing both local and remote control using various devices including PC's, Mobile Phones, Tablets, etc. You could use anything with a web browser and local network or internet access in fact. Programming of the PLC's is done using easy to learn xLogic Soft Function Block Diagram Software which is a [free download from here.](https://www.rievtech.com/download.html) You can also download Manuals, regular PLC updates and a bunch of other useful items as well.

The Scada product I chose was [myScada](https://www.myscada.org/en/). When I first started using the product it was at Version 4 and was still in beta development. As such they offered a 'free for personal use' unlimited 'tags' and PLC connections product which was fantastic. As time went by they also developed iOS and Android apps which in the early days were quite good and relatively bug free. Surprisingly they also included quite good technical help for free.

Unfortunately mySCADA changed to become a very expensive (and very buggy) platform with the arrival of Version 7. They no longer offered a useful free to use version but as I had become a satisfied user I chose to pay for a 500 tag, unlimited PLC connection version to accommodate my project which had well over 300 tags and 4 PLC's. They now offered a paid tech support service for premium support and a free tech support service without any real support unfortunately.

## Home-Assistant

It was after installing [Home-Assistant](https://www.home-assistant.io/) on a QNAP TS-453 Pro NAS that I realized I might actually be able to use it as a viable alternative to a buggy, poorly supported and overpriced SCADA product.

As [Home-Assistant natively supports Modbus](https://www.home-assistant.io/components/modbus/) I started with a spare PLC and set it up with a small program with examples of switches, binary sensors and sensors to check that my migration would be possible.

This first test worked well however I soon realised there was a [problem with having multiple modbus clients](https://community.home-assistant.io/t/ability-to-add-multiple-modbus-hubs/16365) and as I have four modbus devices requiring four modbus hubs then that was a real problem for me. Luckily for me there was a [workaround](https://community.home-assistant.io/t/multiple-tcp-modbus-slaves/99210/2) which had been [developed by PtP](https://community.home-assistant.io/u/PtP) so I set about testing that with a second PLC and it worked seamlessly. The final two PLC's were also added and I flicked the switch off on the myScada server for good. The best news came when [support for multiple modbus hubs and writing to registers was added to the 0.88.0 release](https://github.com/home-assistant/home-assistant/pull/21238).  

[Modbus](https://www.home-assistant.io/components/modbus/) | [Modbus Binary Sensors](https://www.home-assistant.io/components/binary_sensor.modbus/) | [Modbus Climate](https://www.home-assistant.io/components/climate.modbus/) | [Modbus Sensor](https://www.home-assistant.io/components/sensor.modbus/) | [Modbus Switch](https://www.home-assistant.io/components/switch.modbus/)
