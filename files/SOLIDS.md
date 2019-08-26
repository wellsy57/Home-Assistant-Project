# Solids Removal and Solids Filtrate Recovery

[LIGHTING](https://community.home-assistant.io/t/lighting-control-pir-sensors-and-occupation/131955) | [IRRIGATION](https://community.home-assistant.io/t/irrigation-and-misting/133716) | [INPUT](https://community.home-assistant.io/t/input-streams/133606) | [TREATMENT](https://community.home-assistant.io/t/treatment-processes/132729) | [FILTRATION](https://community.home-assistant.io/t/filtration-streams/133086) | SOLIDS | [PLC](https://community.home-assistant.io/t/plc-programming/133839) | [myHome-Assistant Project](https://community.home-assistant.io/t/myhome-assistant-project/131756)

There are six separate solids recovery streams which need to be dealt with. 

* **Shadehouse Swirl and Bio-Filtration solids**
* **Pump Area Swirl and Bio-Filtration solids**
* **Pump Area Sand Filtration backwash solids**
* **Lower Pond Bio-Filtration solids**
* **Activated sludge solids**
* **Lower Pond to Shadehouse Flooded Pipe**

The system which allows me to filter out the solids and recover the solids filtrate consists of 6x200L polythene drums which are linked by 25mm drum connectors to allow first settling then filtration and finally automated pumping to retreat the filtrate by treatment in the Activated Sludge System.

![SolidsRemovalSystem|368x500](upload://i71I7keBSev8ve962reDYN1z8TH.jpeg) 

The above system can turn the below left sample to become the below right sample in a just a few hours.

![BackwashFeed-SolidsFiltrateDischarge|690x350](upload://2gbKQfOfD1C9DjMuY93QwpxE3qc.jpeg) 

Each 'batch' consists of around 400-500L of sludge/water liquor which is held to settle out for up to 12 hours depending on its settleability.
In most cases 95% of solids have settled in 3-4 hours but I usually allow around 6-8 hours for up to 98% to settle.

![SolidsRemovalSystemSettlingTank|690x396](upload://usKcFYJYpytZ9Ih6TKYcTo6SLGZ.jpeg) 

At that time the settled liquor (in the Settling Tanks) is allowed to run into the the Settled Tanks where a fine stainless steel mesh filter covered in white polythene filter material filters out most of the remaining sludge particles as it passes into the Solids Filtrate Tank.

![SolidsRemovalSystemSettledTank|666x500](upload://75euHD6bjaGMlXlHpIWEACKfiBc.jpeg)


![SolidsRemovalSystemSolidsFiltrateTank|628x500](upload://1gnpV38cWM1LQ4SxEu5ckU7722.jpeg)   

The clear liquor (or Solids Filtrate) is then pumped from the Solids Filtrate Tank to my Storm Water Sump in a controlled manner whereby pumping stops at high level in the storm water sump.
This then is forwarded to the Grey Water Sump as the Treatment System is able to handle intake.

It usually takes around 4-6 hours for the 400-500L of Solids Filtrate to be run into the Treatment System depending on any other inflows at the time.

The below Grafana trend shows the past 24hrs tank levels. Overnight the system was empty but receiving minor inflows. At around 0730 this morning I backwashed the sand filter to fill the Settling Tank (green trendline). As the Settling Tank filled to overflow into the Settled Tank (orange trendline) you can see at 0810 the rise in level of that tank and the subsequent rises as my solids removal system sends the waste stream to the settling tanks. The sudden drop later in the day is when the Settled Tank is released to the Solids Filtrate Tank.

![UltrasonicSolidsRemovalGrafana|690x344](upload://uoWJ4iylz2MilFYl629A69liC2O.jpeg) 

Every 2-3 weeks the bulk settled sludge is removed to further separate the water from the sludge. This is done when the Solids Removal System is 'empty'. By pumping the 100-150 odd litres left in the Settling Tanks to again settle out the solids in another separate 200L polythene drum. That settled liquor is then pumped back into the Settled Tanks and filtered as normal.

At that point the remaining bulk settled sludge consists of around 20-30L quantity. This waste is then either sent to my compost bins or pumped directly to the sewerage system.

[myHome-Assistant Project](https://community.home-assistant.io/t/myhome-assistant-project/131756)
