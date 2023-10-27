## EPC 1522 and EPC 1502 Quick Reference Guide TEST <br>
#####  Version: FW 2023.0 LTS
---

![Banner_FW2023](/FW_2023/images/Banner_FW2023_0_LTSg.jpg) <br>
FW 2023.0 LTS available, update your EPC now! - The Update File can be found here: <br>
[EPC 1502 FW2022](https://www.phoenixcontact.com/product/1185416) <br>
[EPC 1522 FW2022](https://www.phoenixcontact.com/product/1185423) <BR>

If you are still using FW 2022 on your EPC, check the [Archive](FW_2022/README.md). <br>
<br>

# Complete Guide for FW 2023.0 LTS:

***#1 SET UP YOUR EPC***

|   #  |  Topic   |  Content   |     |
| --- | --- | --- | --- |
| 1 | [Introduction](FW_2023/Configuration/00_FAQ_FW2023.md) | What is new with FW 2023.0 LTS <br> Functions and Features of your EPC 15x2 with Firmware 2023.0 LTS |
| 2 | [Firmware-Update to 2023.0 LTS](/FW_2023/Configuration/01_UpdateInstruction23.md) | Instruction on how to update your EPC to FW 2023.0 LTS 
|   3  |  [Configurations](FW_2022/Configuration/0_Installation.md)   |  First steps with your EPC,[Installing the Device](FW_2022/Configuration/0_Installation.md), Functions of the new [Edge-Cockpit](https://www.plcnext.help/te/WBM/WBM.htm), [Network-Configuration](/FW_2023/Configuration/02_Network.md), Profinet, [WLAN (wireless)](/FW_2023/Configuration/02_Network.md) and configuration of your Interfaces like [DisplayPort](/FW_2023/Configuration/03_DisplayPort.md) and [USB-Ports](/FW_2022/Configuration/5_USB.md) | 
| 4 | [NEW! Backup & Restore an App to another EPC](/FW_2023/Configuration/04_BackUp_App_Container.md) | Example on how to backup a whole Node-RED (or InfluxDB, or Grafana,...) into an .app container and restore the whole application on another EPC |



<br>

***#2 COLLECT AND ANALYSE DATA FROM THE FIELD***

|   #  |  Topic   |  Content   |     |
| --- | --- | --- | --- |
| 1 | [Collect data from the field](/FW_2022/EdgeFunctions/1_CollectingData.md) |       Collect data from the field via numeros protocolls like [REST](/FW_2023/Node-RED/Examples/2_REST_to_InfluxDB.md), [OPC UA](/FW_2023/Node-RED/Examples/1_OPCUA_Demo.md), [Modbus RTU](/FW_2021_ARCHIVE/02_ModbusToInfluxDB.md) and many more |
| 2 | Examples with Node-RED | [Read data from Node-RED and store it in a local CSV-file](/FW_2022/Code/Node-RED_Examples/3_Read_Data_from_InfluxDB_to_CSV.md) <br> [Send a daily report (CSV) via E-Mail](/FW_2022/Code/Node-RED_Examples/4_Send_CSV_via_Email.md)|
| 3 | [New! Passwort Protect your Node-RED App](/FW_2023/Node-RED/01_PasswortProtect_Node-RED-App.md) | Passwort protect your Node-RED App to secure it from unauthorised access |

***#3 ANALYSE AND PROCESS DATA LOCAL IN INFLUXDB 2.0***
|   #  |  Topic   |  Content   |     |
| --- | --- | --- | --- |
| 1 | [Install InfluxDB 2.0](/FW_2023/InfluxDB/00_Install_InfluxDB.md) | Install InfluxDB from the PLCnext Store | 
| 2 | [Set up InfluxDB 2.0 Database](/FW_2022/Code/Influx2/Influx_Configuration.md) | Set up your Organisation and Secuity settings, create a bucket to store data from the field inside the database | 
|3| [Alerting](/FW_2022/Code/Influx2/InfluxDB_Alerts.md) | Analyse your data with a "threshold check" or a "deadman check", send alerts via a handler  | 
|4| [Telegraf](/FW_2022/Code/Influx2/Telegraf_Configuration.md) | Configure InfluxDB 2.0 Telegraf agent for collecting and reporting metrics with a vast library of input plugins |
|5| [Backup & Restore data to a Windows-Host-PC](/FW_2022/Code/Influx2/Backup_Restore.md) | Backup data from a bucket of the EPC, transfer and restore the bucket to a Windows-Host-PC to store and analyse the data on your Windows-PC.  |
|6| [InfluxDB Templates](/FW_2022/Code/Influx2/Templates.md) | Install predefined Templates for InfluxDB & Telegraf. Example of installing the "Network Interface Monitoring" Template into InfluxDB and Telegraf. |
|7| [Grafana Dashboards](/FW_2023/InfluxDB/10_Grafana.md) | Visualise your InfluxDB data with Grafana |

***#4 SEND DATA TO ANY CLOUD***
|   #  |  Topic   |  Content   |     |
| --- | --- | --- | --- |
| 1 | [Influx to Proficloud.io](/FW_2022/Code/Cloud/InfluxDB_to_Proficloud.md) | Read data from InfluxDB and send it to Phoenix Contact's Proficloud.io. <br> Free of charge for up to 20 metrics!  |
| 2 | [Influx to any Cloud](/FW_2022/Code/Cloud/InlfuxDB_to_AnyCloud.md) | Read data from InfluxDB and send it into any Cloud. |
| 3 | [Set up your EPC for AWS](/10_AWS_QuickstartGuide.md) | Complete set up for AWS Cloud |
| 4 | [Set up your EPC for MS Azure](/11_Azure_QuickstartGuide.md) | Complete set up for Microsoft Azure Cloud|

***#5 USE PLCNEXT ENGINEER FOR IEC-61131 PROGRAMMING***

|   #  |  Topic   |  Content   |     |
| --- | --- | --- | --- |
| 1 | [IEC programming with PLCnext Engineer](/FW_2022/Code/PLCnext%20Engineer/1_UsePLCnextEngineer.md) | Use your EPC for IEC-61131 programming, import your EPC to PLCnext Engineer, insert the EPC to an existing project|



***#6 APPS*** 
|   #  |  Topic   |  Content   |     |
| --- | --- | --- | --- |
| 1 | [Docker-Portainer App](/FW_2021_ARCHIVE/08_DockerPortainer.md) | Installation of the Docker-Portainer App for easy integration of containers on a graphical user interface. |
| 2 | [Device and Update Management App](/FW_2022/Apps/DeviceAndUpdateManagement.md) | Manage the software of devices supporting an OPC UA server, secured connection to the devices and the update of the firmware. |
| 3 | [thinedge.io Cumulocity IoT](/FW_2022/EdgeFunctions/2_Cumulocity_IOT.md) | The EPC 1502 and EPC 1522 are certified Cumulocity IoT devices. <br> Via the thinedge.io App connectivity to many IoT platforms including Cumulocity IoT, Azure IoT can be done easily. |





## Contributing

You can participate in this project by [submitting bugs and feature requests](https://github.com/PLCnext/OSSTemplate/issues). Help us by checking *this guide* how bugs are reported.
Please let us know if anything is not working out as expected.

## Feedback

* Ask a question in our [Forum](https://www.plcnext-community.net/index.php?option=com_easydiscuss&view=categories&Itemid=221&lang=en).
* Request a new feature on [GitHub](CONTRIBUTING.md).
* File a bug in [GitHub Issues](https://github.com/PLCnext/CSharpSamples/issues).

## License

Copyright (c) Phoenix Contact Gmbh & Co KG. All rights reserved.

Licensed under the [MIT](LICENSE) License.