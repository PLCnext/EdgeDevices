# Quick Reference Guide<br>

## Collect data via REST from PLCnext

> **SourceCode can be found [here](/FW_2022/Code/Node-RED/REST_Demo_to_Influx.json)

The easiest way to collect data from any PLCnext device is via the REST protocol. 
That includes data that is generated on the "OT" side of your EPC (PLCnext Engineer) or also any PLCnext device in the field.

> Since the REST nodes are not pre-installed on your EPC, a internet connection is required to install those nodes.

## 1. Prepare the PLCnext data of the Field-device
In the PLCnext Engineer project all GDS ports or PLC variables can be accessed 
with the REST interface when the "HMI" flag is approved.

The "HMI" flag of each variable that should be read by Node-RED of the EPC has to be set.

For **local** Variables, simply set the "HMI" flag in the program: <br>
![Local_Variable_REST](/FW_2022/images/Local_HMI.JPG) <br>

For **global** Variables, you have to right-click on the variable and confirm "create HMI tag" or select the variable and click on the "HMI" tab symbol above. <br>
![Global_Variable_REST](/FW_2022/images/Global_HMI.JPG) <br>

Also, if you want to create a secured connection (User authetification), you must enable the "PLCnext user management": <br>
![Secured_WBM](/FW_2022/images/Secured_WBM.JPG) <br>


> Deeper information about REST can be found  <br>
 [here](https://www.plcnext.help/te/Service_Components/REST_data_interface/REST_data_interface_Introduction.htm) <br>


## 2. Install the REST nodes from the Node-RED Palette-Manager 
If you use the [Node-RED App for EPC 1502](https://www.plcnextstore.com/permalinks/apps/latest/60002172000676) or  [for 1522](https://www.plcnextstore.com/permalinks/apps/latest/60002172000678) the REST nodes come pre-installed, therefore Step 2. can be skipped.  <br>
If you are using a general Node-RED instance without nodes pre-installed, the REST nodes can be installed via the palette-manager: <BR>
![Install_REST](/FW_2022/images/Install_REST.gif) <br>

The package will install new nodes to your Node-RED: <br>

![Installed_REST](/FW_2022/images/REST_installed..JPG) <br>

## 3. Use the nodes to read data into InfluxDB
1. Please import the [ExampleFLow](/FW_2022/Node-RED/REST_Demo_to_Influx.json) 
 We will focus on the "read-node" to read data from any PLCnext device into the local InfluxDB database of the EPC. <br>
![REST_ExampleFlow](/FW_2022/images/REST_ExampleFlow.JPG) <br>
2. Configure the "InfluxDB Batch Insert" node. Set up your organisation and bucket-name as you have [configured it in InfluxDB](/FW_2022/Influx2/Influx_Configuration.md) <br>
3. Configure the "plc-read-variables" node. All it needs, is to set the username and passwort (printed). <br>
![Edit_Rest_Node](/FW_2023/images/Rest2023_Config.JPG) <br>
After doing so, deploy the flow. <br>

>Attention! - Since FW 2023.0 LTS, even if the REST variables of the localhost (EPC) are to be read, the full IP address (example: 192.168.1.10) of the localhost must be entered. It is no longer possible to enter "localhost" as the host IP.

4. After a first deployment, the "plc-red-variables" node should show a "connected" status. <br>
Open up the "plc-read-node" again and set any variable you want to read. You can use the search-bar to set any variable or open up the drop-down menu and set multiple variables to read. <br>
![Select_REST](/FW_2022//images/Select_REST.JPG) <br>
In my example, 10 variables are read. Since those 10 variables should be written into InfluxDB in an Array, the node "Combine multiple output into one" has to be set to 10 messages: <br>
![Combine_REST](/FW_2022//images/Combine_REST.JPG) <br>
5. The data will now be written into the local InfluxDB database.
With this method, a hige amount of data (huge amount of variables) can be read into the local database with minimal effort and with the exact same flow that is as small as shown above. <br>
I can now analyse and pre-process the data in InfluxDB Chronograf. <br> <br>
You'll need to configure the InfluxDB node! - Please see here: [Configure InfluxDB database](/FW_2023/InfluxDB/00_Install_InfluxDB.md) <br>
![Influx_RESTdata](/FW_2022//images/Influx_RESTdata.JPG) <br>