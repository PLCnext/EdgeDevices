# Quick Reference Guide<br>

## Send a daily report (csv-file) via E-Mail

> **SourceCode can be found [here](../Node-RED/DailyReport_via_Mail.json)**

In chapter [Read data from InfluxDB and write its value into a CSV-File](/FW_2022/Code/Node-RED_Examples/3_Read_Data_from_InfluxDB_to_CSV.md) a CSV-File was created and stored with variables. <br>
In this step, this CSV-File should be send via a SMTP server to an e-mail adress of a technician for a daily report. <BR>

![DailyReport1](../../images/DailyReport1.jpg) <br>

1. In oder to use the e-mail nodes needed, you need to install the "node-red-node-email" package from the Palette Manager.<br>
![DailyReport2](../../images/DailyReport2.jpg) <br>

2. Import the [attached flow](../Node-RED/DailyReport_via_Mail.json) <br>

3. Select what file should be attached to your email via the "get file" node. <br>
In my example the CSV-File created before "CSVTest.csv" inside the folder /opt/plcnext/CSV/ will be attached. <br>
You can change the function node "write email" accordingly to your required text. <br>
4. The sending mail-address needs to be logged in (via password). <br>
Set your username and passwort. <br> The receiver just needs a mail-address <br>