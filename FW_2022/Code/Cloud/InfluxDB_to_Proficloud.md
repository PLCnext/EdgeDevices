# Quick Reference Guide<br>

## Send data into Proficloud
<BR>

> **SourceCode can be found [here](../Node-RED/InfluxToProficloud.json)**

>To learn about the Proficloud.io from Phoenix Contact, please visit: <br>
https://proficloud.io/e-learning/ 
<br> <br>
Especially start the courses: <br>
[Node-RED and Proficloud.io](https://proficloud.io/e-learning/get-to-know-node-red-and-proficloud-io/) <br>
and <br>
[Connect the Machine Manager to Proficloud.io](https://proficloud.io/e-learning/connect-the-machine-manager-to-proficloud-io/)

1. Inside the Proficloud.io, create a new "Virtual Device" to create a new UUID. <br> This process is also descibed in the above links. <BR>
2. Import the [JSON SourceCode](../Node-RED/InfluxToProficloud.json) in Node-RED. <br>
![Influx_to_Proficloud1](../../images/Influx_PCloud1.JPG) <br>
3. Set the vitual UUID you just created inside the "ProficloudDevice" Node. <br>
4. Configure the InfluxDB "Read data" node. <br>
In my example, all data inside the bucket "PLCnext" will be read. <br>
The data of the last 10 seconds "(start: -10s, stop: -1s)" are summarized in a sampling rate of 1s "every 1s, fn: mean". <br>
Change the settings according to your application. <br>
![Influx_to_Proficloud2](../../images/Influx_PCloud2.JPG) <BR>
<BR>
If you want to only read some data out of a single InfluxDB bucket, you can do so by setting filters inside the query. <br>
![Influx_to_Proficloud3](../../images/Influx_PCloud3.JPG) <br>

5. Read the data from InfluxDB and write data into Proficloud.io using the inject node "timestamp".

If everything was configured correct, switch to Proficloud.io and assign your metrics. <br> Each variable send to the cloud has to be assigned to a metric to be able to log those inside the Time Series Database of the Prodicloud.io. <br>
![Proficloud_Metrics](../../images/Proficloud_Metrics.JPG) <br>

Assign each variable you want to work on to a metric. <br>

>For small-scale application with up to 20 metrics (variables), the Proficloud.io is completely free of charge! <br>

![Proficloud_Metrics_Assigned](../../images/Proficloud_Metrics_Assigned.JPG) <br>

Switch to the "Time Series Data Service" and create a Dashboard with the data you just assigned to a metric.
![Proficloud_TSDB](../../images/Proficloud_TSDB.JPG) <br>
![Proficloud_TSDB](../../images/Proficloud_TSDB_config.JPG) <br>