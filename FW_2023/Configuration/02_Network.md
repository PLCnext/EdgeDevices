# Quick Reference Guide<br>

## Installing Node-RED on EPC 15x2

All Network configuartions are now to be found ordered inside the tab "Network" under "Configuration" inside the Web Based Management. <br>

### Configure the Ethernet-Ports X2 and X3 
Default configuration: <br>
X3 - LAN1 - 192.168.1.10 **PROFINET CONTROLLER** <br>
X2 - LAN2 - 192.168.2.10 **PROFINET DEVICE** <br>

All changes are applied after a reboot. <br>
![X3_X2_Settings](/FW_2023/images/X2_X3_ETH.jpg) <br>

### Configure the WIFI (wireless ethernet)
The WLAN can be used as a client to establish a wireless connection with an access point or router. <br> Either set up a static IP address or set the configuration to DHCP. If DHCP was activated, only the name of the network as well as its password needs to be entered. Once rebooted, the device should be connected to the router and was given an IP address.
![WIFI_config](/FW_2024/images/DHCP_WIFI.JPG) <br>

### Configure the Default Route (**Important for internet access**)
If you want to access the internet with any ETH-Port or via WIFI, you'll need to set the "Default Route" under "Additional Settings" to the port that is connected to your Router. <br>
![DfaultRoute](/FW_2023/images/DefaultRoute.JPG) <br>
