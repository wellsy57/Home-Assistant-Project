# Home-Assistant Project

[HOME](https://github.com/wellsy57/Home-Assistant-Project/blob/master/files/LIGHTSYS.md) | [ENERGY](https://github.com/wellsy57/Home-Assistant-Project/blob/master/files/ENERGY.md) | [TREATMENT](https://github.com/wellsy57/Home-Assistant-Project/blob/master/files/TREATMENT.md)| [CONTROL](https://github.com/wellsy57/Home-Assistant-Project/blob/master/files/CONTROL.md)

This is a place for me to document my home automation systems and processes.

## Background

I'm an Electrical Fitter/Mechanic with a wide range of experience but an interest leaning towards automation and control. 

Aside from work, my own personal journey into automation really began when I moved my family from a remote location in north Queensland to a suburban home south of Brisbane. After constructing a new shadehouse I realised that (due to work commitments eating into my free time) I really needed to automate the watering and misting of my extensive plant collection. 

Initially I installed an off the shelf irrigation controller but things quickly progressed to a more refined programmable timer system. Later I began utilizing a couple of [Eaton Mini PLC's](https://www.eaton.com/SEAsia/ProductsSolutions/Electrical/ProductsServices/AutomationControl/Automation/ModularProgrammableLogicControllers/index.htm) to build my own custom irrigation and misting controller with more precise misting control. This system was equipped with a simple LED Mimic Panel which I divised to allow operators (the wife or kids) to diagnose system status faults for me. This was usually in conjunction with phone calls at night to me as I was often working away. Very soon I began to recognise that I also needed remote monitoring and control capability.

So I moved on to higher spec [Rievtech PLC's.](https://www.rievtech.com) My system was expanding beyond irrigation, misting and water storage to include water treatment, solar power monitoring and outside lighting control.

To fulfil those needs I chose the Rievetech PLC's because they were well priced, easily expandable and equipped with with [ethernet connectivity](https://en.wikipedia.org/wiki/Ethernet) using the [Modbus Protocol.](https://en.wikipedia.org/wiki/Modbus) I was now able to include a [SCADA system](https://en.wikipedia.org/wiki/SCADA) with local and remote control by various devices including PC's, Mobile Phones and Tablets. Programming of the PLC's is easy to learn and very intuitive using the xLogic Soft - Function Block Diagram Software which is a [free download from here.](https://www.rievtech.com/download.html) You can also download Manuals, regular PLC updates and a bunch of other useful items as well.

## But why PLC's?

[PLC's](https://en.wikipedia.org/wiki/Programmable_logic_controller) have been a large part of my professional life as an electrician so I naturally looked at options for automation using them for my own purposes. These days there are also a large range of very affordable Mini PLC's available which are not quite industrial grade but are still built to very high standards.

The one key feature for me is that: PLC's operate autonomously with a high degree or reliability and accuracy. 

Operator input can be implimented via local switch inputs (Local Control Station or LCS), [HMI Panels](https://en.wikipedia.org/wiki/User_interface) or a networked supervisory system (SCADA) which can allow advanced remote monitoring and control functions. Failure of the HMI Panels or communications network does not necessarily stop the process controls, and on resumption of communications the operator can continue with monitoring and control. If all critical sensors, switches, instruments, etc are hard wired to the PLC and the PLC program is carefully designed, then any unsafe outcomes will halt the process autonymously with no user intervention required. If the control system remains down for long periods the operators can always use local control stations (LCS) to halt any unsafe equipment operation OR terminate the whole process.

## Scada

The SCADA (SUPERVISORY, CONTROL and DATA AQUISITION) product I chose to impliment was [myScada](https://www.myscada.org/en/). When I first started using the mySCADA product it was at Version 4 and still in beta development. As such the makers offered a free for personal use, unlimited tags and PLC connections product which was really fantastic. As time went by they also developed very affordable iOS and Android apps which were quite good and relatively bug free. Surprisingly they also included very good technical help for free.

Unfortunately mySCADA changed to become a very expensive and very buggy platform with the arrival of Version 7. They no longer offered a useful free to use version but as I had become a satisfied user I chose to pay for a 500 tag, unlimited PLC connection version to accommodate my project which had well over 300 tags and 4 PLC's which were equipped with 15 expansion devices. MySCADA now offered a paid tech support service for 'premium support' and a free tech support service 'without any real support' unfortunately. The final straw for me was when Version 8 arrived and I wanted to shift my software to new physical server. I received zero help with procurement of a new Product Key which was required to install on the new server.

So the search began for a better solution to my SUPERVISORY, CONTROL and DATA AQUISITION needs which ended up (perhaps surprisingly) being Home-Assistant.

## Home-Assistant

I purchased a Raspberry PI 3 b+ and setup some Sonoff Basic switches flashed with Tasmota as a first test and quickly realized how powerful HA was. What really thrilled me was the incredible wealth of community help for seemingly every problem that arose.

My only concern was how long it took to reboot the PI. I could literally go and boil the kettle and make a cup of coffee every time a restart of the PI was required.

By contrast, I can upload a completely new PLC program from my PC>PLC across my network and restart the PLC in 20 seconds or so.

After some more research I realised that HA could also be installed on a higher spec machine as well.

It was after installing [Home-Assistant](https://www.home-assistant.io/) on a [QNAP TS-453 Pro NAS](https://www.qnap.com/en-au/product/ts-453%20pro) that I realized I might actually be able to use it as a viable alternative to a buggy, poorly supported and overpriced mySCADA product.

As [Home-Assistant natively supports Modbus](https://www.home-assistant.io/components/modbus/) I started the next test to see if my PLC'S were compatible. I used a spare PLC and set it up with a test program with examples of switches, binary sensors and sensors to check that moving would be possible.

My initial modbus testing worked well however I soon realised there was a [problem with having multiple modbus clients](https://community.home-assistant.io/t/ability-to-add-multiple-modbus-hubs/16365) and as I have four modbus devices requiring four modbus hubs then that was a real problem for me. Luckily for me there was a [workaround](https://community.home-assistant.io/t/multiple-tcp-modbus-slaves/99210/2) which had been [developed by PtP](https://community.home-assistant.io/u/PtP) so I setup the spare PLC along with the first of my four system PLC's and they worked seamlessly with the workaround. Next the final two PLC's were also added and I confidently flicked the switch off on the myScada server for good. The best news came when [support for multiple modbus hubs and writing to registers was added to the 0.88.0 release](https://github.com/home-assistant/home-assistant/pull/21238).  

## My Guiding Automation Principles

1. Always include local lockout where malfunction of automation or control could cause unsafe conditions as a consequence.

2. Always ensure all equipment is installed and maintained in a safe manner.

3. Never allow remote control or supervisory systems to override a local lockout.


[Modbus](https://www.home-assistant.io/components/modbus/) | [Modbus Binary Sensors](https://www.home-assistant.io/components/binary_sensor.modbus/) | [Modbus Climate](https://www.home-assistant.io/components/climate.modbus/) | [Modbus Sensor](https://www.home-assistant.io/components/sensor.modbus/) | [Modbus Switch](https://www.home-assistant.io/components/switch.modbus/)
