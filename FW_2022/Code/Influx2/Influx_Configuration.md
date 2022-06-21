# Quick Reference Guide<br>

## InfluxDB 2.0 Chronograf Configuration

With FW 2022.0 - InfluxDB 2.0 Chronograf is pre-installed on your EPC

You have to set a username and passwort when first starting InfluxDB. <br>
Also, you have to set a "Organisation" name. <br>
In the below example, my username was set to "admin" and the organisation was set to "PxC".

## How to read data from the field from Node-RED
Our goal is, to read data from the field (via PLCnext Engineer or Node-RED) and then store those data in InfluxDB 2.0 to analyse and pre-process the data. <br>

1. First, go to "Data" --> "Buckets" and create a new bucket. <br>
The created bucket will be used to store all incoming data. <br>
Set a "Retention Policy" which defines how long the data should be stored. <br>
    >Attention, if you safe a lot of data into this bucket, configure the Retention Policy in a way that the storage of your EPC will not be written full.

    ![InfluxDB_Bucket](../../images/InfluxDB_Bucket.JPG) 
    <br>


2. To be able to write data from Node-RED to InfluxDB 2.0, you have to set a "Token". <br>
Eather create a new Token "+ Genearte Token" or use the default "admin's Token" in Node-RED. <br>
    ![AdminToken](../../images/Influx_AdminToken.JPG)  <br>
Copy the value of your Token. <br>
    ![AdminTokenValue](../../images/AdminTokenValue.JPG) <br>

3. After you have collected data in Node-RED using any Protocoll (OPC UA, REST, Modbus, ...) your require (Can be found [here](../../EdgeFunctions/1_CollectingData.md)), the InfluxDB Node has to be configured. <br>
    ![InfluxNode1](../../images/Influx_Node1.JPG) <br>
Edit the InfluxDB batch node. Set the Organisation and Bucket name as set in your InfluxDB database. <br>
    ![InfluxNodeEdit](../../images/Influx_Node2.JPG) <br>
Next, set the properties of the node (Pencil button on the right) <br>
Paste the "admin's Token" or any self-configured Token. <br>
    ![InfluxNodeProperties](../../images/Influx_Properties.JPG) <br>
Deploy your changes. <BR>

4. As result, you should now be able to see the incoming data in InfluxDB. 
All data can be seen in the "Explore" tab. <br>
You can then create dashboards, alerts and scripts to downsample and analyse your data.
![InfluxDataExplorer](../../images/Influx_Data.JPG) <br>
<br>


Please see next chapter: [Alerting with InfluxDB](InfluxDB_Alerts.md)




