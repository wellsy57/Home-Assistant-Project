[LIGHTING](https://community.home-assistant.io/t/lighting-control-pir-sensors-and-occupation/131955) | [IRRIGATION](https://community.home-assistant.io/t/irrigation-and-misting/133716) | [INPUT](https://community.home-assistant.io/t/input-streams/133606) | [TREATMENT](https://community.home-assistant.io/t/treatment-processes/132729) | [FILTRATION](https://community.home-assistant.io/t/filtration-streams/133086) | [SOLIDS](https://community.home-assistant.io/t/solids-filtrate-recovery/133450) | PLC
[myHome-Assistant Project](https://community.home-assistant.io/t/myhome-assistant-project/131756)

This is the start of some information I would like to pass on for those who may be interested in looking at how PLC's may be used in your automations.

I would first like to repeat what I mentioned earlier in my introduction to my project.
"The one key feature for me is that: PLC’s operate autonomously with a high degree or reliability and accuracy."

Given this ability to use all the logic you have built in to your program, the PLC can then continue to function safely while many other systems may fail for various reasons (HA server, Router, MQTT server, Node-Red server, etc) around the PLC system. Due to the PLC system being wired and programmed as a discrete system it will remain working as long as it has (in my case) 24VDC control power for the PLC and 240VAC to run any connected/controlled devices.

In a system where you are looking for 100% reliability this is a must have characteristic.

## xLogic Soft

First I would like to give a brief look at the programming software I use. [xLogic Soft is a free download](https://www.rievtech.com/download.html) and once installed and open on your desktop it looks like the below screenshot. You don't need to own any PLC's to start having a go at designing a new program. It is specific to [Reivetech PLC's](https://www.rievtech.com/) so if you like another brand of PLC you will need to checkout it's related software.

![xLogicFullScreenshot|690x418](upload://sVzZAZJx5Sx3BO7PstSbL26FAKm.jpeg) 

In the above image you can see I have a project open called Master PLC 54 (Top Left) and that I am looking at a "Simulation" of the actual PLC (at the bottom of the image) which is displayed powered up with a program status message on the LCD screen telling the user the name of the PLC, which Slot number the PLC is and that it is in the RUN state with No Faults. Note that the PLC used in this program also has 5x expansion modules connected which increases the available Inputs and Outputs substantially.

Below is a two page chunk of the complete program which shows the relatively simple Storm Water Sump Pump control system.

![xLogicStormWaterScreenshot|690x233](upload://wkJpQc03vKM6YEJosQUJ1DXb2zb.jpeg) 

The whole program (Master PLC 54) runs to 68 pages (1267 KB) presently. This PLC has had quite a bit of development on it since it came online around 2011 and I only rename at major updates.

![xLogicStormWaterPG1Screenshot|690x481](upload://sn1ZG1AoAuElj58aRpqRV9exHkJ.jpeg) 

If you look closer at the Function Blocks on the page (see above Page 1 of Storm Water Control) you may be able to see one of the features which make this program quite useful when connecting up your sensors, binary sensors, switches, etc, in Home assistant. If you look closely at the F21 Digital Flag labeled as 'Auto Empty Start' then to the lower left there is a listing which reads Modbus_0x=1556(614H). The important information to connect that to HA is '1556' which is the coil number. This PLC is Slot 3 (as shown on the LCD screen above) and is Static IP

## HA Integration (the short story)

With those two pieces of information I can setup this 'Flag' in HA as a modbus switch in my config.
The IP address is also required to setup the Modbus Hub but that is beyond the scope of this discussion for now.


```
      - name: Storm Water Auto Empty
        hub: hub3
        slave: 3
        coil: 1556
```

Easy as that!
You can add a bunch of items or one at a time to the HA config but HA must be restarted to bring the new device/devices online and then you will simply need to add your new 'entity' to your Lovelace UI.

## Function Block Diagrams (or 'Blocks')
This software is based on the user picking up 'Blocks' from the 'Workspace' and dragging them to where you want to place them on the 'Circuit Diagram'. You then begin wiring up the connections to other 'Blocks' until you build a working program.

As a sparky who is used to working with electrical schematics this software came easily to me but I also had to develop more skills with logic boxes of Boolean algebra. Anyone used to that will find it even easier.

The key thing which makes the whole process of creating your programs easy (fun even) is that at any moment you can choose to 'simulate' your program which will power up the simulated PLC and give you a chance to see whats working, OR NOT?

Even better, once the program is uploaded to the PLC the software can be connected to monitor the running program live to the PC. When problems need to be diagnosed this feature is priceless as you can scroll around the program you have constructed and read the actual process values. Even the buttons on the PLC can be operated as if you were in front of the PLC.

More coming shortly.....!

[myHome-Assistant Project](https://community.home-assistant.io/t/myhome-assistant-project/131756)
