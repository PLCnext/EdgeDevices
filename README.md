# Edge PC EPC 1502/1522 Quickstart Guide

[![License](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)
[![Web](https://img.shields.io/badge/PLCnext-Website-blue.svg)](https://www.phoenixcontact.com/plcnext)
[![Community](https://img.shields.io/badge/PLCnext-Community-blue.svg)](https://www.plcnext-community.net)

The Edge PC repository is a collection of various sample code for Node-RED for Edge PC:

1185416 – EPC 1502 

1185423 -  EPC 1522 

Each example explains one or more topics on how to use Nodes and Function in the pre-installed Node-RED.

## Getting Started

1. Connect the power-supply to your EPC
2. Connect your Host-PC to X2-LAN, open up your cockpit during the first start-up using the URL: "192.168.2.10/cockpit"
3. Configure your network. Profinet can only be used with X3-LAN interface.
   The IP-address can be changed in the "Extended Configuration" tab inside your cockpit.
4. See the chapter below to create your IoT usecase!

## Edge-Cockpit
To start any function on the EPC, make sure your Host-PC is connected via Ethernet and configured in the same network.
Open up a webbrowser (e.g. Google Chrome) and open-up the Edge-Cockpit:
<b>ip-adress/cockpit </b>
(default X2-Ip adress: 192.168.2.10/cockpit) <br>

![Cockpit](images/00_CockpitS.jpg) <br>
<br>
<br>
## Quickstart-Guide

|   #  |  Topic   |  Content   |     |
| --- | --- | --- | --- |
| 0 | [Introduction to EPC & Cockpit](99_EPC15x2_Introduction.md) | Benefits of Edge Computing <br> Functions and Features of your EPC 15x2 |
|   1  |  [Node-RED](07_Node-RED_HowTo.md)   |  Learn Node-RED within the Edge PC with basic node functions <br> Guidance on how to connect PLCnext with Node-RED and InfluxDB  <br> Collection of Example Flows   | 
|  2   | [InfluxDB Database](09_InfluxDB.md)    | Configuration of the InfluxDB database <br> How to create a dashboard <br> How to create an alert management  |
|  3   | [Docker-Portainer](08_DockerPortainer.md)    | Installation of Docker Portainer on your EPC <br> How to deplay containers  | 
|  4   | [AWS Quickstart Guide](10_AWS_QuickstartGuide.md)    | Quickstart and Information how to connect your EPC 15x2 to AWS Cloud <br> Using Pre-installed MQTT nodes to connect to AWS  | 
|  5   | [Mircosoft Azure Quickstart Guide](11_Azure_QuickstartGuide.md)    | Quickstart and Information how to connect your EPC 15x2 to Microsoft Azure Cloud <br> Using Pre-installed MQTT nodes to connect to Azure  | 

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