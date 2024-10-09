## Factory-Reset while boot-up [FW 2024.0 required on EPC]
<br>

**Important: Your EPC must be runnning FW 2024.0 to be able to factory-reset via the below steps!**

If you have no access to your EPC anymore to start a factory-reset via the WBM, you can now start a factory-reset while booting up the device. 
This will help you, if you can't log in to your EPC or simply forgot the credentials. 

1. Plug in a DisplayPort-Monitor and a USB-keyboard to your EPC 15x2. <BR>
2. Plug in power (24V) to your EPC. You should see some boot-up information on your local monitor. 
3. After just some seconds, you should see the "GRUB" menu. Where "Linux A" | "Linux B" and "Recovery" are listed. Do not choose any option here! Without any input, wait until this "GRUB" menu is gone. 
4. Once this menu is gone, **hold** the "SHIFT" key and **rapidly** press the "R" button. <BR>
After a very short period of time, you should be able to see the "PLCNEXT EMERGENCY RECOVERY MODE". <BR>
![Recovery1](/FW_2024/images/RecoveryS1.png)
<BR>
5. Type "Yes" and press enter. <BR>
Now select which type of recovery you want to perform (RESET or RECOVER) <BR>
RESET: All user data will be deleted (settings, users, passwords, programs) <BR>
RECOVER: Complete factory-reset, this might downgrade your firmware if you ever updated the device. Make sure you install the most current Firmware ater a factory-reset.  <br>

![Recovery2](/FW_2024/images/RecoveryS2.png) <BR>

6. You will be asked to confirm the recovery again. Enter "Y" to start the recovery. Please be patient and do not disconnect the power. The device will reboot on its own once the process is done. <BR>
7. Once the device is through the recovery process, you can connect to the EPC using its default IP adress again: X3 - 192.168.1.10 <bR>


 > Any IP-address, PLCnext Engineer project or app, as well as potentionally any FW-update you installed previosly will be deleted. The device can be reached via the defualt IP again (X3: 192.168.1.10) <BR>

 > After starting the recovery process, do not plug the power (24V) and wait several minutes (up to 20min)! The device could then be connected via the default IP address (X3: 192.168.1.10).
 <br>
<BR>

>After a recovery, please make sure to update your EPC to firmware-version 2024.0 again, since this feature can only be performed with FW 2024.0 LTS!