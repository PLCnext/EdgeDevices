## Factory-Reset while boot-up [FW 2024.0 required on EPC]
<br>

If you have no access to your EPC anymore to start a factory-reset via the WBM, you can now start a factory-reset while booting up the device. 
This will help you, if you can't log in to your EPC or simply forgot the credentials. 

1. Plug in a DisplayPort-Monitor and a USB-keyboard to your EPC 15x2. <BR>
2. Plug in power (24V) to your EPC. You should see some boot-up information on your local monitor. 
3. After just some seconds, you should see the "GRUB" menu. If you don't press any button on your keyboard, the PLCnext linux will be booted normally. <BR>
If you however want to perform a factory reset, select the "recovery" partition using the arrow keys and press enter. <BR>
This will now start the recovery process. Any IP-address, PLCnext Engineer project or app, as well as potentionally any FW-update you installed previosly will be whiped. <BR>

![FactoryReset](/FW_2024/image.png)




> After selecting the "recovery" partition, do not plug the power (24V) and wait several minutes (up to 20min)!

>After a recovery, if needed update your EPC to firmware-version 2024.0 again, since this feature can only be performed with FW 2024.0 LTS!