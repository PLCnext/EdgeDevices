# Quick Reference Guide<br>

## Firmware Update from FW 2023.0.x LTS to FW 2024.0 LTS
<br>



1. Download the Update folder from the Phoenix Contact Homepage under "Downloads" --> "Firmware Update": <br> [EPC 1502 FW2024](https://www.phoenixcontact.com/product/1185416) <br>
[EPC 1522 FW2024](https://www.phoenixcontact.com/product/1185423) <BR>


2. Reconnect to the WBM again and open up the tab"Administration" --> "Firmware Update" <br>
Browse the previous downloaded (.raucb) Firmware-file and press "Start". <br>
![Update_Firmware](/FW_2023/images/Update_Firmware23.jpg) <br>
Once the EPC is done installing, reconnect to the WBM and check if FW 2023.0 is now installed. <br>

> **Do not shut-off the power while the EPC is updating! The EPC will restart automatically. The Update can take up to 20 minutes.**


Since Apps like Node-RED, Grafana or InfluxDB are installed inside a container, a FW update will not interrupt or change anything inside each App. 
Those should function after the Firmware-Update as they did before.
