# Quick Reference Guide<br>

## Programm an IEC61131 Programm (OT) with PLCnext Engineer
<BR>

>Important <br>
You need at least PLCnext Engineer version 2023.3 to be able to  use all new features from FW 2023.0 LTS!

>The EPC 1502 and EPC 1522 are unable to save retain data in case of sudden power-loss. <br> The values of retain variables are only stored in a periodical cycle of 10 minutes.

You are new to PLCnext Engineer? <br>
All information about PLCnext and the PLCnext Engineer can be found inside the [PLCnext Info Center](https://www.plcnext.help/te/Where_to_start/PLCnext_Beginners_Guide.htm) <br>

PLCnext Engineer can be installed [here](https://www.phoenixcontact.com/de-de/produkte/programmier-software-plcnext-engineer-1046008). <br>

The EPC 1502 and EPC 1522 can be programmed via PLCnext Engineer. Control application can be developed, but also data can be collected through the variety of protocols.

## Import the Library to PLCnext Engineer
To be able to use your EPC with PLCnext Engineer, you fist must import the "Edge PC" library. <br>
![Engineer_Import](/FW_2022/images/Engineer_Import.JPG) <br>

After importing the library, you should see a new folder in "Network" called "Edge PC".  <br>
![Engineer_Network](/FW_2023/images/Engineer23_2.jpg) <br>

Select the right device and firmware-version and import the Controller to your application.

> If you want to use your EPC as Profinet Controller or Device, make sure ETH-Port "X3 - LAN1" or "X2 - LAN2" is used.

If you are used to any PLCnext Controller, you will have no issue using the EPC, as it functions the same. <br>
Just remember that no retain handling is supported. The EPC only stores retentive data cyclically and does not save the value of the variable in the event of a voltage loss. <br>
Also important is that the realtime behaviour can be influenced by Node-RED, InfluxDB or Docker. <br>

## I have an existant PLCnext Project, how do I change the PLC to an EPC?

With PLCnext Engineer, the controller can also be exchanged in an existing project at any time. <br>
To do so, first select and copy your EPC from the right side "Network". <br>
![Engineer_Switch1](/FW_2022/images/Engineer_Switch1.JPG) <br>

Afterwards, right click on your existing controller on the left side and click "replace". <br>
![Engineer_Switch2](/FW_2022/images/Engineer_Switch2.JPG) <br>

If you require any other help, please refer to https://elearning.plcnext.help/PLCnEng_Basics/story_html5.html <BR>