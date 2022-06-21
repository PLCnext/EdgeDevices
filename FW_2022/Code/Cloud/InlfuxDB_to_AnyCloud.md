# Quick Reference Guide<br>

## Send data into AnyCloud
<BR>

> **SourceCode can be found [here](../Node-RED/InfluxDB2_to_Cloud.json)**

To be able to send any data from the internal InfluxDB database, import the SourceCode attached above. <br>

![Cloud_NodeRed](../../images/Cloud_NodeRed.JPG) <br>

The "InfluxDB IN" node will be used to read data from the internal InfluxDB database. Configure the organisation, and set the admin token as descibed in the [InfluxDB Configuration](). <br>
Inside the Query, the path to the data must be set. <br>
Set the bucket-name, the retention-policy and the name of your data. <br>

![Proficloud_SourceCode](../../images/Proficloud_NodeSettings.JPG) <br>

For a more detailed explanation, see also: <br>
[Configure and send data into Proficloud](InfluxDB_to_Proficloud.md) <br>
[Configure and send data into AWS](../../../10_AWS_QuickstartGuide.md) <br>
[Configure and send data into MS Azure](../../../11_Azure_QuickstartGuide.md) <br>