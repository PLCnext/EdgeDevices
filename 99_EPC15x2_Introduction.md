## Quick Reference Guide<br>
### For
## Phoenix Contact: EPC 1522 and EPC 1502
 
### Version: 1.2
---
# Edge PC EPC15x2 Introduction 
# Functions & Features of the Edge Cockpit

## What is Edge Computing?
An Edge PC processes data closer to where it is generated, instead of processing it in the Cloud - with great benefits in Latency, bandwith of your network and secruity!
>Edge Computing is the practice of capturing, storing, processing and analyzing data near the client, where the data is generated. <br>

![EPC_Featres](images/EPC_Features_wn.png)

The Edge PCs of Phoenix Contact are the perfect tools for your IoT development.
>To the products: <br>
https://www.phoenixcontact.com/product/1185416   EPC 1502<br>
https://www.phoenixcontact.com/product/1185423   EPC 1522



![EPCIntro](images/EPC_Intro.png)

The EPC combines the functionality of a traditional PLC (programable via PLCnext Engineer) with all featured protocals like Profinet, OPC UA, Modbus,... <br>
and the functionality of an IoT device. <BR>
Software like Node-RED or Influx-DB are pre-installed with easy integration.
With Docker-Portainer unlimited use-cases can be served.

# Starting the Edge Cockpit

To start any function on the EPC, make sure your Host-PC is connected via Ethernet and configured in the same network.
Open up a webbrowser (e.g. Google Chrome) and open-up the Edge-Cockpit:
<b>ip-adress/cockpit </b>
(default X2-Ip adress: 192.168.2.10/cockpit)
![Cockpit](images/0_Cockpit.jpg)
>From here you can start any Function like Node-RED, Docker-Portainer or the InfluxDB Databaseadministration.

## Functions of the Edge Cockpit

|   #  |  Topic   |  Content  |  
| --- | --------- |  --------- |
| ![WBM](images/x1_WBM.png) |  PLCnext WBM | Web Based Management for PLCnext <br> Firmware Update / User configuration / Firewall / LDAP <br> PLCnext Store administration / PROFICLOUD administration  | 
| ![ExtendedConfig](images/x2_ExConfig.png) |  Extended Configuration IoT | Network Configuration / Date & Time for Database <br> Node-RED Configuration / USB enable or disable <br> Reboot  |
| ![Node-RED](images/x3_NodeRED.png) | Node-RED | Start Node-RED to programm a flow-based IoT program<br> Further information and example flows can be found here: <br> [Node-RED Example-Flows](07_Node-RED_HowTo.md) |
| ![InfluxDB](images/x4_InfluxDB.png) | InfluxDB Database | Start InfluxDB Database <br> Save and administrate data, create rules how to handle data or events <br> Further information can be found here: <br> [InfluxDB Database](09_InfluxDB.md)|
| ![Docker-Portainer](images/x5_Docker.png) | Docker-Portainer | Start Docker-Portainer to administrate and add containers <br> Further information and how to install Docker-Portainer form the PLCnext Store can be found here: <br> [Docker-Portainer Installation](08_DockerPortainer.md)|
| ![Cloud](images/x6_Cloud.png) | Cloud-Connection | The EPC 15x2 offers a variety of cloud connections <br> Quickink to AWS Console, Microsoft Azure and Google Cloud Platform |
| ![Visualisation](images/x7_Visu.png) | Visualisation |Quicklink to PLCnext Engineer Visualisation|