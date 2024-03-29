# Quick Reference Guide<br>

## Collect data via OPC UA from the field

> **SourceCode can be found [here](/FW_2022/Code/Node-RED/OPCUA_Taglist_toInflux.json)**

The OPC UA Taglist Node is now preinstalled on your EPC. <br>
With the OPC UA Taglist Node, you can connect to any OPC UA Server and read huge amount of data (variables) with just one node.

## 1. Prepare the OPC UA Server
Make sure that the OPC UA Server supports OPC UA to be able to connect with the EPC-Client.

> Important! Make sure the time configured on the EPC (can be configured with PLCnext Engineer) matches the time configured on the OPC UA Server. <br>
If the time doesn't match, the certificates may be rejected from the Server.

## 2. Configure the OPC UA Tagnode
1. Import the [ExampleFlow](/FW_2022/Node-RED/OPCUA_Taglist_toInflux.json) <br>
![OPCUA_Tagnode](/FW_2022/images/OPCUA_Tagnode.JPG) <br>
2. Configure the OPC UA Tagnode. <br>
Set the "Endpoint" to the Serveradress. In the example below, the adress ("opc.tcp://192.168.1.10:4840") is the OPC UA Server of the EPC. 
Also, the "Topic" may change if you connect to a non-Phoenix Conatct device.  <br> 
![UA_TagnodeConfig](/FW_2023/images/Taglist2023.JPG) <br>

    > Note: Please be aware, that the topic has changed to "ns=6" with FW 2023.0 LTS. <br>

    Also, further extand the configuration (Pencil button) and set the required security setting. <br>
![UA_TagnodeConfig2](/FW_2023/images/Taglist_config2.jpg) <br>

3. Configure the OPC UA Client node
Configure the "OPC UA Client" node and set the same "Endpoint" and "Topic" and Security settings. <br>

4. Configure the "InfluxDB Batch Insert" node. Set up your organisation and bucket-name as you have [configured it in InfluxDB](/FW_2022/Influx2/Influx_Configuration.md) <br>

## 3. Use the OPC UA Tagnode 
1. If all configurations are done correctly, deploy your changes. <br>
The OPC UA Taglist should show the status "Done", the OPC UA Client should show the status "session active".
2. If the OPC UA Client successfully connected to the OPC UA Server, the OPC UA Tagnode should now list all available OPC UA variables found on the server. <br> Select all required variables in the list, accept by clicking "Done". <br>
![OPCUA_Tagnode_Vars](/FW_2023/images/Taglist_vars.jpg). <br>

    >Attention! - Since FW 2023.0 LTS, even if the REST variables of the localhost (EPC) are to be read, the full IP address (example: 192.168.1.10) of the localhost must be entered. It is no longer possible to enter "localhost" as the host IP.

3. In my example, 10 variables are read. Since those 10 variables should be written into InfluxDB in an Array, the node "Combine multiple output into one" has to be set to 10 messages: <br>
![Combine_REST](/FW_2022/images/Combine_REST.JPG) <br>

4. The data will now be written into the local InfluxDB database.
With this method, a hige amount of data (huge amount of variables) can be read into the local database with minimal effort and with the exact same flow that is as small as shown above. <br>
I can now analyse and pre-process the data in InfluxDB Chronograf. <br>
![Influx_UAdata](/FW_2022/images/Influx_UAdata.JPG)

> Troubleshoot: If your OPC UA Client node can not connect to your OPC UA server "rejected by OPC UA Server" please check the configured time (in WBM or similar) of the client and server. The time of both have to be somewhat the same, otherwiese the certificates both exchange to each other is invalid! <br>
You can also change the configured time of the EPC using PLCnext Engineer. 