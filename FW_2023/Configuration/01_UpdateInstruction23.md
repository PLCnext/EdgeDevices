# Quick Reference Guide<br>

## Firmware Update to FW 2023.0 LTS
<br>

>Attention! The Update to FW 2023.0 can only be done with >HW01 devices! <br>

>If you currently have a Node-RED project or InfluxDB project running with FW2022.0, it will be kept after the firmware update to FW 2023.0 LTS. <br> 
However, saved passwords and configurations of the individual nodes will be lost and must be redeployed after the update. <br> Any updated or installed Node from the Palette Manager will also be lost and needs to be reinstalled.

1. Initial situation: Connect to the WBM (default: X1 - 192.168.1.10) <br>
Make sure your device has a hardware revision of at least HW01. <br>
![HW_RevWBM](/FW_2022/images/Update_Ausgangslage.JPG) <br>

2. Download the "PreUpdate App" version 2023.0 from the [PLCnext Store](https://www.plcnextstore.com/eu/app/1564). Alternatively the app is also stored inside the firmware-update folder ".zip" you downloaded from the Phoenix Contact Homepage. <br>
   
3. Install the App "PreUpdate 2023" via the WBM. Select the rauc.b Update-File and press "Start". <br>
Your EPC will reboot and and sets the necessary changes for the update. <BR>
![UpdateWBM](/FW_2023/images/Pre-Update_App2023.jpg) <br>

4. Download the Update folder from the Phoenix Contact Homepage under "Downloads" --> "Firmware Update": <br> [EPC 1502 FW2023](https://www.phoenixcontact.com/product/1185416) <br>
[EPC 1522 FW2023](https://www.phoenixcontact.com/product/1185423) <BR>



5. Reconnect to the WBM again and open up "Administration" --> "Firmware Update" <br>
Browse the previous downloaded (.raucb) Firmware-file and press "Start". <br>
![Update_Firmware](/FW_2023/images/Update_Firmware23.jpg) <br>
Once the EPC is done installing, reconnect to the WBM and check if FW 2023.0 is now installed. <br>

> **Do not shut-off the power while the EPC is updating! The EPC will restart automatically. The Update can take up to 20 minutes.**

6. OPTIONAL <br>
Since the "PreUpdate" App is no longer needed, the App can be stopped and deleted from the system. 



> Attention! <br>If you never used the native Node-RED or InfluxDB software on your device runnning FW 2022.0, those software are deleted after the update. Newer versions of [Node-RED](https://www.plcnextstore.com/permalinks/apps/latest/60002172000676) and [InfluxDB](https://www.plcnextstore.com/permalinks/apps/latest/60002172000677) can be installed from the PLCnext Store. <br>

>Attention! 
If you are updating your device directly from FW 2021.0 to FW 2023.0,
the native Node-RED and InfluxDB software are also deleted and can be reinstalled from the PLCnext Store. In oder to keep your flows, FW 2022.0 needs to be installed first.
