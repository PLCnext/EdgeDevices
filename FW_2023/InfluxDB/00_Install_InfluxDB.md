# Quick Reference Guide<br>

## Installing Node-RED on EPC 15x2

> InfluxDB is no longer pre-installed on the device. <br>
This gives you the flexibility to install the version you require and the possibility to develop your program on one device and multiply it quickly and easily to a plurality of EPCs. <br>

1. Choose the version of InfluxDB you require from our PLCnext Store. <br>
Newer Versions will be constantly uploaded. <br>
[InfluxDB for EPC 1502 & EPC 1522](https://www.plcnextstore.com/permalinks/apps/latest/60002172000677) <br>


2. Offline-Installation: <br> 
Download the InfluxDB App from the PLCnext Store. <br> 
Open up the Web Based Management of your EPC and install the App under "Administration" --> "PLCnext Apps". <br>
![Install_App](/FW_2023/images/Install_App23.jpg) <br>

3. Once the App is uploaded and installed on the EPC, you need to start the App container next. <br>
![Start_App](/FW_2023/images/Install_App_Start.jpg) <br>

    > It might occur, that the Web Based Management is unresponsable after starting the App. Please wait a short period of time and reload the WBM. <br>
    The App should be runnning afterwards. <br>

4. Once the App Status changed to "RUN", it can be opened via the Port 8086. <br> (Default: X3 - 192.168.1.10:8086) <br>

The App can now of course be accessed and visualised via the local DisplayPort directly. <br>
<br>
<br>
