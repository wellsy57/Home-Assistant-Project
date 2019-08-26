[LIGHTING](https://community.home-assistant.io/t/lighting-control-pir-sensors-and-occupation/131955) | IRRIGATION | [INPUT](https://community.home-assistant.io/t/input-streams/133606) |  [TREATMENT](https://community.home-assistant.io/t/treatment-processes/132729) | [FILTRATION](https://community.home-assistant.io/t/filtration-streams/133086) | [SOLIDS](https://community.home-assistant.io/t/solids-filtrate-recovery/133450) | [PLC](https://community.home-assistant.io/t/plc-programming/133839) | [myHome-Assistant Project](https://community.home-assistant.io/t/myhome-assistant-project/131756)

## Irrigation Control
Irrigation Control was really where it all began for my personal interest in automation.
Things started out quite simply with off the shelf controllers and 13mm solenoids for a fairly basic system however my passion for growing plants took hold and my needs became much greater.

These days I have scaled back completely on the propagation of plants and really only need two areas with automated watering so my Home-Assistant UI reflects that.

![IRRIGATIONscreenshot%20(2)|690x390](upload://uRNmhJkTiARkQAoHUjrNDOH52il.png) 

Also, as I have recently migrated my monitoring and control system from a SCADA system to Home-Assistant I will also share a couple of (now retired) mySCADA UI screenshots to give you some idea of what the existing PLC program can do if required. The program still exists on the PLC...while the solenoids and control relays ade still ready to go...just not being used ATM. These screenshots depict development screens and one has some 'comms' errors so please bear with me? Not terribly long ago there were three irrigation areas and two misting areas were required. With the below UI all that functionality could be controlled and monitored.

![myScadaIrrigationMisting01|690x414](upload://iWoRzKh0ZBemCrScbPNGi1M30vB.png) 

The above UI shows the Irrigation system is OFF as no operating mode has been selected AND there is no duration set. The mist is ON and the shadehouse centre area is being misted for 12 seconds while the pump running is the Treated Water Pressure Pump.

![myScadaIrrigationMisting|690x304](upload://iVVYIqqlW4I2IPJtDoOUVLLWlrY.png)

The above UI shows the Irrigation system is ON and is set to start at 0800. The mode selected is 'Every second day' with the first day down so watering will trigger tomorrow for the shadehouse area for 15 minutes. Misting is also ON from 0700 - 1700 to run every 15 minutes for 20 seconds on the shadehouse walkway only. Mist is being run by the Treated Water Pressure Pump as the Rain Water Tank is selected due to it being low level (4500L).

[myHome-Assistant Project](https://community.home-assistant.io/t/myhome-assistant-project/131756)
