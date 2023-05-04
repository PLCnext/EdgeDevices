# Quick Reference Guide<br>

## Installing Node-RED on EPC 15x2

> Node-RED is no longer pre-installed on the device. <br>
This gives you the flexibility to install the version you require and the possibility to develop your program on one device and multiply it quickly and easily to a plurality of EPCs. <br>

1. Choose the version of Node-RED you require from our PLCnext Store. <br>
Newer Versions of Node-RED will be constantly uploaded. <br>

[NODE-RED for EPC 1502](...) <br>
[NODE-RED for EPC 1522](...) <br>

2. Offline-Installation: <br> 
Download the Node-RED App from the PLCnext Store. <br> 
Open up the Web Based Management of your EPC and install the APP under "Administration" --> "PLCnext Apps". <br>
![Install_App](/FW_2023/images/Install_App23.jpg) <br>

3. Once the App is uploaded and installed on the EPC, you need to start the App container next. <br>
![Start_App](/FW_2023/images/Install_App_Start.jpg) <br>

    > It might occur, that the Web Based Management is unresponsable after starting the App. Please wait a short period of time and reload the WBM. <br>
    The App should be runnning afterwards. <br>

4. Once the App Status changed to "RUN", it can be opened via the Port 1880. <br> (Default: X3 - 192.168.1.10:1880) <br>
![Access_App](/FW_2023/images/Node-REDinstalled.jpg) <br>
The App can now of course be accessed and visualised via the local DisplayPort directly. <br>
<br>
<br>
## Deinstalling Node-RED on EPC 15x2
If you for instance require a newer version of Node-RED than currently installed, Node-RED as well as any other PLCnext Store App can be deinstalled inside the Web Based Management.

Connect to the Web Based Management and navigate to "Administration" --> "PLCnext Apps".  <br>
Stop the App you want to deinstall via the "Stop" button. <br>
The App can now be uninstalled via the "Uninstall" button. <br>

