## Factory-Reset while boot-up [FW 2024.0 required on EPC]
<br>

If you have no access to your EPC anymore to start a factory-reset via the WBM, you can now start a factory-reset while booting up the device. 
This will help you, if you can't log in to your EPC or simply forgot the credentials. 

1. Plug in a DisplayPort-Monitor and a USB-keyboard to your EPC 15x2. <BR>
2. Plug in power (24V) to your EPC. You should see some boot-up information on your local monitor. 
3. After just some seconds, you should see the "GRUB" menu. Once that is shown, repeatedly press the "SHIFT" + "R" buttons on your keyboard. 
4. Confirm that you want to proceed with the factory reset to start the recovery. <BR>
 Any IP-address, PLCnext Engineer project or app, as well as potentionally any FW-update you installed previosly will be deleted. <BR>

 > After starting the recovery process, do not plug the power (24V) and wait several minutes (up to 20min)! The device could then be connected via the default IP address (X3: 192.168.1.10).
 <br>

![FactoryReset](/FW_2024/image.png)
<BR>

>After a recovery, please make sure to update your EPC to firmware-version 2024.0 again, since this feature can only be performed with FW 2024.0 LTS!