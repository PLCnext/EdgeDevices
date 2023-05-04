# Quick Reference Guide<br>

## Programm an IEC61131 Programm (OT) with PLCnext Engineer
<BR>

If you are interested in creating a visualisation with more functionality and user roles, a Grafana visualisation might make sense. <br>
Grafana is a multi-platform open source analytics and interactive visualization web application. It provides charts, graphs, and alerts for the web when connected to supported data sources.

## Install Grafana on your EPC
1. Download and install the PLCnext Store App [**Grafana for x86**](https://www.plcnextstore.com/permalinks/apps/latest/60002172000509). <br>
The App can be installed via the Web Based Management. <br>

2. Once you have started the App, Grafana can be opened via Port :53000 <br> (default: X3 - LAN1: 192.168.1.10:53000) <br>

3. If you have data already stored in InfluxDB, you can now add InfluxDB as your data source. <br>
To do so, navigate to "Configuration" and click on "Add data source". <br>
Select InfluxDB as your data source. <br>
![Grafana_DataSource](/FW_2023/images/Grafana_1.jpg) <br>
<br>
Configure all needed information to get access to your buckets inside InfluxDB. <br>
![Grafana_DataSource2](/FW_2023/images/Grafana_2.jpg) <br>
<br>
You can test wheter any bucket can be read from Grafana. <br>

4. Now that we successfully tested the connection and were able to read our buckets from InfluxDB, a dashboard can be created to visualise our data. <br>
Via "Flux" you need to select individual variables from a bucket that should be visualised. <br>
![Grafana_DataSource3](/FW_2023/images/Grafana_3.jpg) <br>
<br>
Here is an example: 

        from(bucket: "edge")
        |> range(start: -3h, stop: -10s)
        |> filter(fn: (r) => r["_measurement"] == "OPCUA_LemonLimeCount)
        |> filter(fn: (r) => r["_field"] == "value")



![Grafana_DataSource4](/FW_2023/images/Grafana_4.jpg) <br>