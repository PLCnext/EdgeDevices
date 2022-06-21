## Quick Reference Guide<br>
### For
## Phoenix Contact: EPC 1522 and EPC 1502
 
### Version: 1.2
---
# InfluxDB Database configuration

InfluxDB is pre-installed on the Edge-PC 15x2. <br>
Data can be administrated, processed or saved locally on the device <br>
Rules can be defined, an alert management can be created. <br>
With Node-RED we can import data from any device in our network, also data from PLCnext Engineer can be imported. <br> To understand how to import data from PLCnext or Node-RED to InfluxDB, please follow the steps on this chapter: <br>
[First Project Example - PLCnext -> Node-RED -> InfluxDB](00_FirstProjectExample.md)

## Usecases with InfluxDB on your EPC 15x2
|   #  |  Topic   |  Content   |     |
| --- | --- | --- | --- |
| 1 | [Dashboards](21_Influx_Dashboards.md) | Create Dashboards with InfluxDB <br> Visualise your data with Template Variables |
|   2  |  [Downsampling Data](22_Influx_Downsampling.md)   |  Save the high precision raw data for only a limited time, and store the lower precision, summarized data longer   | 
|   3  |  [Alerting](22_Influx_Alerting.md)   |  Create Alerts if a variable is off the intended, create e-mail or server messages   | 

