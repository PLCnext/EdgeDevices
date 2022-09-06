## Quick Reference Guide<br>
### For
## Phoenix Contact: EPC 1522 and EPC 1502
 
### Version: FW 2022.0.7
---




![Banner_FW](/FW_2022/images/NewFW_Banner2.JPG) <br>
FW 2022.0 available, update your EPC now! - The Update File can be found here: <br>

[EPC 1502 FW2022](https://www.phoenixcontact.com/product/1185416) <br>

[EPC 1522 FW2022](https://www.phoenixcontact.com/product/1185423) <BR>


If you are still using FW 2021 on your EPC, check the [Archive](FW_2021_ARCHIVE/README.md). <br>
<br>

# Complete Guide for FW 2022.0:

***#1 SET UP YOUR EPC***

|   #  |  Topic   |  Content   |     |
| --- | --- | --- | --- |
| 1 | [Introduction](FW_2022/99_Introduction_FW2022.md) | Benefits of Edge Computing <br> Functions and Features of your EPC 15x2 with Firmware 2022.0 |
| 2 | [Firmware-Update to 2022.0](/FW_2022/Configuration/2_FirmwareUpdate.md) | Instruction on how to update your EPC to FW 2022.0 
|   3  |  [Configurations](FW_2022/Configuration/0_Installation.md)   |  First steps with your EPC,[Installing the Device](FW_2022/Configuration/0_Installation.md), Functions of the new [Edge-Cockpit](FW_2022/Configuration/1_EdgeCockpit.md), [Network-Configuration](/FW_2022/Configuration/3_Network_Configuration.md), Profinet, [WLAN (wireless)](/FW_2022/Configuration/3_Network_Configuration.md) and configuration of your Interfaces like [DisplayPort](/FW_2022/Configuration/4_DisplayPort.md) and [USB-Ports](/FW_2022/Configuration/5_USB.md) | 
| 1 | [NEW! Password protect Node-RED ](FW_2022/99_Introduction_FW2022.md) | Password protect Node-RED against unauthorized access from the network. <br> Especially important when accessing the internet with your EPC!  |


<br>

***#2 COLLECT AND ANALYSE DATA FROM THE FIELD***

|   #  |  Topic   |  Content   |     |
| --- | --- | --- | --- |
| 1 | [Collect data from the field](/FW_2022/EdgeFunctions/1_CollectingData.md) |       Collect data from the field via numeros protocolls like [REST](/HW02/Code/Node-RED_Examples/2_REST_Demo.md), [OPC UA](/HW02/Code/Node-RED_Examples/1_OPCUA_Demo.md), [Modbus RTU](/FW_2021_ARCHIVE/02_ModbusToInfluxDB.md) and many more |
| 2 | Examples with Node-RED | [NEW! Read data from Node-RED and store it in a local CSV-file](/FW_2022/Code/Node-RED_Examples/3_Read_Data_from_InfluxDB_to_CSV.md) <br> [NEW! Send a daily report (CSV) via E-Mail](/FW_2022/Code/Node-RED_Examples/4_Send_CSV_via_Email.md)|

***#3 ANALYSE AND PROCESS DATA LOCAL IN INFLUXDB 2.0***
|   #  |  Topic   |  Content   |     |
| --- | --- | --- | --- |
| 1 | [Set up InfluxDB 2.0 Database](/FW_2022/Code/Influx2/Influx_Configuration.md) | Set up your Organisation and Secuity settings, create a bucket to store data from the field inside the database | 
|2| [Alerting](/FW_2022/Code/Influx2/InfluxDB_Alerts.md) | Analyse your data with a "threshold check" or a "deadman check", send alerts via a handler  | 
|3| [Telegraf](/FW_2022/Code/Influx2/Telegraf_Configuration.md) | Configure InfluxDB 2.0 Telegraf agent for collecting and reporting metrics with a vast library of input plugins |
|4| [NEW! Backup & Restore data to a Windows-Host-PC](/FW_2022/Code/Influx2/Backup_Restore.md) | Backup data from a bucket of the EPC, transfer and restore the bucket to a Windows-Host-PC to store and analyse the data on your Windows-PC.  |

***#4 SEND DATA TO ANY CLOUD***
|   #  |  Topic   |  Content   |     |
| --- | --- | --- | --- |
| 1 | [Influx to any Cloud](/FW_2022/Code/Cloud/InlfuxDB_to_AnyCloud.md) | Read data from InfluxDB and send it into any Cloud. |
| 2 | [Influx to Proficloud.io](/FW_2022/Code/Cloud/InlfuxDB_to_AnyCloud.md) | Read data from InfluxDB and send it to Phoenix Contact's Proficloud.io. <br> Free of charge for up to 20 metrics!  |
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
| 2 | [NEW! Device and Update Management App](/FW_2022/Apps/DeviceAndUpdateManagement.md) | Manage the software of devices supporting an OPC UA server, secured connection to the devices and the update of the firmware. |





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