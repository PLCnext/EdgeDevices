# Quick Reference Guide<br>

## Collecting data via Node-RED to store it in InfluxDB
<br>
The main goal of the EPC is to collect data from the field, analyse the data locally to then send the processed data into any cloud or server.

The examples below will help you to collect data from the field. <br>
By using own-developed nodes for OPC UA and PLCnext REST you can now collect a huge amount of data as easy as never! <br>

**Please select the Protocoll you require, a detailed explaination with Source Code will then open** 


|  #  |  Protocol to collect data   |  Content   |   
| --- | --- | --- | 
| 1 | [OPC UA](../Code/Node-RED_Examples/1_OPCUA_Demo.md) | **NEW!** Collect a huge amount of data with just one "OPC UA Tagnode" <BR> Variables from any OPC UA Server can simply be selected from a Drop-Down menu and written into InfluxDB to safe them locally.  |
| 2 | [PLCnext REST](../Code/Node-RED_Examples/2_REST_Demo.md) | **NEW!** Best solution if you collect data from any PLCnext Controller in the field! <br> Collect a huge amount of data from the PLCnext side of the EPC itself or from multiple PLCnext PLCs in the field. <BR> Variables from any PLCnext device can simply be selected from a Drop-Down menu and written into InfluxDB to safe them locally.  |
| | |
| 3 | [Modbus RTU](../../FW_2021_ARCHIVE/02_ModbusToInfluxDB.md) | Collect data from Modbus Serial Devices (4-wire to 4-wire RS-485 withou Auto-RTS-Toggle limited) <br> EPC 1522 required  |
| 4 |[Basic Nodes](../../FW_2021_ARCHIVE/01_BasicFlow.md)|Learn Node-RED within the Edge PC with basic node functions. Common and function nodes like "Inject","Debug","Switch" nodes are described.|



## Import Example-flows into Node-RED of your EPC 1502/1522
1. Open-up and copy the source code (just the long string) of any example-flow (CNTRL + C) <br>
![CopyFlow](../../FW_2021_ARCHIVE/images/N_ExampleCopy.JPG)
2. <p> Connect to your Edge-PC via Ethernet and open the Edge-Cockpit. <br>
    Default: http://192.168.2.10/wbm </p>
3. <p> Open Node-RED </p>
4. Click on the "Import" button on the right upper corner. <br>
![Import_Flow](../../FW_2021_ARCHIVE/images/Import_Node.jpg) </p>
5. Paste the string to the "Clipboard" and import the flow <br>
![Select_Flow](../../FW_2021_ARCHIVE/images/N_ImportFlow.jpg) </p>

Please see next chapter: [Configre the internal Database](/FW_2022/Code/Influx2/Influx_Configuration.md)