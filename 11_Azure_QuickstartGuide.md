---
platform: {PLCnext Linux Yocto}
device: {EPC 1502 / EPC 1522}
language: {english}
---

# Connect your EPC1502 / EPC 1522 device to your Azure IoT services

> **[Example SourceCode](/FW_2021_ARCHIVE/SourceCode/Quickstart_Flows/QuickGuideFlows/InfluxDB_to_AWS.json)**

# Table of Contents

-   [Introduction](#Introduction)
-   [Prerequisites](#Prerequisites)
-   [Prepare your Device](#Prepareyourdevice)
-   [Connect to Azure IoT](#ConnecttoAzureIoT) 
-   [Integration with Azure IoT Explorer](#Explorer)
-   [Additional Links](#AdditionalLinks)


<a name="Introduction"></a>
# Introduction
**About this document** <br>
This document describes how to connect the Edge-PC EPC 1502 and EPC 1522 running PLCnext Linux Yocto with Azure IoT SDK. This multi-step process includes:

-   Configuring Azure IoT Hub
-   Registering your IoT device
-   Provisioning your devices on Device Provisioning service 
-   Build and deploy Azure IoT SDK on device

<a name="Prerequisites"></a>
Prerequisites

You should have the following items ready before beginning the process:

-   [Prepare your development environment](https://github.com/Azure/azure-iot-sdk-c/blob/master/doc/devbox_setup.md)
-   [Setup your IoT hub](https://github.com/robertalorro/azure-iot-device-ecosystem/blob/master/setup_iothub.md)
-   [Provision your device over DPS](https://docs.microsoft.com/en-us/azure/iot-dps/about-iot-dps)

<a name="Prepareyourdevice"></a>
# Prepare your Device
## Set up your hardware
Choose the desired mounting method and follow the appropriate 
procedure.

### Wall mount
Order No. [1147655](https://www.phoenixcontact.com/product/1147655) <br>
The EPC 15x2 can be attached to a flat surface in a wall-mount orientation using the four key holes. The mounting surface must be flat and 
not subject to vibration.
>NOTE:
The EPC 15x2 must be installed with the connectors oriented 
down to allow the convection cooling to function efficiently <br>

 Installation:
 1.  Attach the two brackets to the EPC... using the included M3x5 
screws.Torque the screws to 0.5 Nm.
2.  Use the EPC 15x2 as a template and mark the locations of the 
mounting holes on the mounting surface.
3. Use the correct anchor type for the mounting surface and securely attach the EPC 15x2 to the wall. Ensure the attaching hardware is in the small section of the mounting holes. <br>
![EPC_Wall_Mount](/FW_2021_ARCHIVE/images/EPC_WallMount.JPG)

### DIN rail mount
Order No. [1147464](https://www.phoenixcontact.com/product/1147464) <br>
1. Install the mounting bracket on the EPC... with the included 
M3x5 screws so the connectors will be oriented downward after 
installation. Torque the screws to 0.5 Nm.
2. Angle the EPC 15x2 so the top edge of the mounting plate hangs on 
the top edge of the DIN rail.
3. Rotate the EPC 15x2 down against the lower edge of the DIN rail. 
Press in until the latch snaps closed.
4. Secure the device on the rail with clamps.
5. If necessary to remove, release the latch using a screwdriver, rotate the bottom of the EPC away, and then lift it straight up off 
the DIN rail. <br>
![EPC_DinRail](/FW_2021_ARCHIVE/images/EPC_DinRail.JPG)

### Connecting the power supply
A removable plug (Order No. [1847055](https://www.phoenixcontact.com/product/1847055) on the EPC 15x2 accepts 
wire sizes of 0.2 ... 2.5 mm² (12 ... 24 AWG).
> NOTE:
To ensure safe operation, use safety extra-low voltage 
(SELV) according to DIN EN 61131 as supply voltage.
This device is protection class I item of equipment.

1. Connect the power conductors to the appropriate terminal in the 
connector.
2. Connect the ground/earth to the screw (5).
3. Insert the connector into the IPC. <br>
![EPC_PS](/FW_2021_ARCHIVE/images/EPC_PowerSupply.JPG)

### Ethernet
Both Ethernet ports have their own MAC address.
> Default IP-address: X2 - 192.168.2.10 /// X3 - 192.168.1.10

The IP-address can be set either with [PLCnext Engineer](https://www.phoenixcontact.com/product/1046008) (PLC 61131 Engineering-Tool) or via Edge-Cockpit (default X2 - 192.168.2.10/cockpit).

> NOTE: Both Ethernet ports can be used to send data into Azure. 
Only X3 can be used for PROFINET.

<a name="Connect to Azure IoT"></a>
# Connect to Azure IoT

Data will be send via Node-RED into MS Azure Cloud.
All needed software and tools come pre-installed with your Edge-PC!

1. All required nodes can be found in the pre-installed nodes of your EPC. <br>
![Azure_Nodes](/FW_2021_ARCHIVE/images/Azure_Nodes.JPG) <br>
2. Please import the [Example SourceCode](SourceCode/Quickstart_Flows/QuickGuideFlows/InfluxDB_to_AWS.json) to Node-RED. <br> 
If you are unsure how to import a Flow into Node-RED, please see the explaination here: [How-To Node-RED](/FW_2022/EdgeFunctions/1_CollectingData.md). <br>
![Azure_Nodes2](/FW_2021_ARCHIVE/images/Azure_Node2.JPG) <br>
3. Create a new IoT device in Azure IoT Hub. <br>
![Azure_Nodes6](/FW_2021_ARCHIVE/images/Azure_Node6.JPG) <br>
Enter the device ID, Key, Protocol in Json script from the IoT device into the first function-node for connecting with Azure IOT Cloud Interface. <br>
  ![Azure_Nodes3](/FW_2021_ARCHIVE/images/Azure_Node3.JPG) <br>
4. Configure Azure IoT Hub Node: <br>
•	Enter Protocol and Hostname in Azure IoT Hub Node. <br>
![Azure_Nodes4](/FW_2021_ARCHIVE/images/Azure_Node4.JPG) <br>
5. Deploy the changes and send a message into Azure IoT Hub.
If your configuration was correct, the status of the IoT Hub node should be "Connected" or "Sent message". <br>
![Azure_Nodes7](/FW_2021_ARCHIVE/images/Azure_Node7.JPG) <br>
You can also receive messages from the cloud to the device using the "Azure IoT Hub Receiver" node. <br>
The connection string can be found in Azure IoT Hub under <br>
"Settings" > "Shared access policies" > "iothubowner" > "Primary connection string". <br>
![Azure_Nodes8](/FW_2021_ARCHIVE/images/Azure_Node8.JPG) <br>

>Another Connection-Example can be seen here: [Node-RED Azure Guide](https://flows.nodered.org/node/node-red-contrib-azure-iot-hub#:~:text=node-red-contrib-azure-iot-hub%20is%20a%20Node-RED%20node%20that%20allows%20you,Hub%20Receiver%20and%20Azure%20IoT%20Hub%20Device%20Twin)

<a name="Explorer"></a>
# Integration with Azure IoT Explorer

Azure IoT Explorer is used to verify the data received from the database. <br> 
1. Go to [Azure IoT explorer releases](https://github.com/Azure/azure-iot-explorer/releases) and expand the list of assets for the most recent release. Download and install the most recent version of the application. <br>
2. For a device, you can either connect your own device, or use one of the sample simulated devices. For some example simulated devices written in different languages, see the [Connect a sample IoT Plug and Play device application to IoT Hub](https://docs.microsoft.com/en-us/azure/iot-develop/tutorial-connect-device) tutorial. <br>
Select the device, you want to see data on and click on telemetry. <br>
Click on "Start" to receive the events. <br>

3. Start IoT Hub and create a new connection "Add connection". <br>
The connection sting can be found in Azure IoT Hub under <br>
"Settings" > "Shared access policies" > "iothubowner" > "Primary connection string". <br>
![Azure_Nodes9](/FW_2021_ARCHIVE/images/Azure_Node9.JPG) <br>

4. Open up your new connection by clicking on the device ID. <br>
Open up the "Telemetry" to see if data is beeing send into Microsoft Azure successfully. <BR>
Start the "Telemetry" by clicking on the "Start" button. <BR>
![Azure_Nodes10](/FW_2021_ARCHIVE/images/Azure_Node10.JPG) <br>

5. Trigger your Node-RED flows to send data into Microsoft Azure. <br>
This data should now be visible in the started "Telemetry" connection. <br>
![Azure_Nodes11](/FW_2021_ARCHIVE/images/Azure_Node11.JPG) <br>

<a name="AdditionalLinks"></a>
# Additional Links

Please refer to the below link for additional information for Plug and Play.

-   [Manage cloud device messaging with Azure-IoT-Explorer](https://github.com/Azure/azure-iot-explorer/releases)
-   [Azure SDK](https://github.com/Azure/azure-iot-sdk-c/blob/master/provisioning_client/samples/prov_dev_client_sample/prov_dev_client_sample.c)
-   [Configure to connect to IoT Hub](https://docs.microsoft.com/en-us/azure/iot-pnp/quickstart-connect-device-c)
-   [How to use IoT Explorer to interact with the device](https://docs.microsoft.com/en-us/azure/iot-pnp/howto-use-iot-explorer#install-azure-iot-explorer)

<br>

Also, feel free to ask your question in our [PLCnext Forum](https://www.plcnext-community.net/en/discussions-2-offcanvas/forums.html).