# Quick Reference Guide<br>

## Firmware Update from FW 2021.0.7 to FW 2022.0
<br>
>Attention! The Update to FW 2022.0 can only be done with >HW01 devices!

To be able to explore all new features of the FW 2022.0, you might have to update your EPC before. <br>

Due to the large amount of changes and improvements made by the firmware update, a little manual pre-preparations are needed beforehand. <br>

The update is larger than any other update file of a PLCnext Controller, which is why you must change the max. UpdateFile-size currently configured in the controller. <br>
This is very easy to do, just install the App ["PreUpdate for EPC15x2"](https://www.plcnextstore.com/eu/app/1564) in WBM.

1. Initial situation: Connect to the WBM (default: X1 - 192.168.1.10) <br>
Make sure your device has a hardware revision of at least HW01. <br>
![HW_RevWBM](../images/Update_Ausgangslage.JPG) <br>

2. Download the "PreUpdate App" from the [PLCnext Store](https://www.plcnextstore.com/eu/app/1564). <br>
   Download the "UpdateFile.raucb" from the Phoenix Contact Homepage: <br> [EPC 1502 FW2022](www.phoenixcontact.com/product/1185416) <br>
   [EPC 1522 FW2022](www.phoenixcontact.com/product/1185423) <BR>

3. Install the App "PreUpdate 2022" via the WBM. Select the rauc.b Update-File and press "Start". <br>
Your EPC will reboot and and sets the necessary changes for the update. <BR>
![UpdateWBM](../images/Update_WBM.JPG) <br>

4. Reconnect to the WBM again and open up "Administration" --> "Firmware Update" <br>
Browse the previous downloaded (.raucb) Firmware-file and press "Start". <br>
![Update_Firmware](../images/Update_Firmware.jpg) <br>
Once the EPC is done installing, reconnect to the WBM and check if FW 2022.0 is now installed. <br>

> Do not shut-off the power while the EPC is updating! The EPC will restart automatically.

> Attention, your data currently stored in InfluxDB 1.8 will be lost after the Update to InfluxDB 2.0!

   
   <br>
   <br>
   
Please see next chapter: [EdgeCockpit](1_EdgeCockpit.md) <br>