# Quick Reference Guide<br>

## Configure the date and timezone on your PLCnext device

The default timezone on a PLCnext device is set to **UTC**. <BR>
While you normally don't face any issue with a "wrong" timezone if using the EPC on its own, this might be a problem when using Grafana or other apps that might come with their own timezone setting. 

<br>
To change the timezone, please follow this guide: <BR>
<BR>

1. Connect to your EPC via SSH ("Putty"). <BR>
2. After logging in as admin, log in as "root" user. <br>
If you haven't created a root user yet, please read the chapter "Using the root user" [here](https://www.plcnext.help/te/Operating_System/Root_rights.htm) <br>
3. Inside the folder /usr/share/zoneinfo you can see all available timezones. <br>
Since my EPC is located in Germany, I will choose "Europe" --> "Berlin" as my timezone.<br>
4. Create the neccecary user right via following command (change the timezone ("/Europe/Berlin") to your required place): <BR>

        ln -sf /usr/share/zoneinfo/Europe/Berlin /etc/localtime

5. Now, open the file "/etc/localtime" with following command:
    
        nano /etc/timezone

6. An empty file will open. In here, enter the same place you choose before. <BR>
In my case, I entered <br>

        Europe/Berlin 

    into the file and saved and closed the file (Cntr + X) 
    
<br>

![ChangeTimezone](/FW_2023/images/timezone.png) <br>

## Now that the timezone is set correct, write the current time into the PLCnext Controller

This can be done by several ways. The easiest might be using PLCnext Engineer. <br>
Connect to your device via PLCnext Engineer and click the "Write time to PLC" button.

![ChangeTime](/FW_2023/images/Changetime.JPG) <br>

Or else, use another option as described [here](https://www.plcnext.help/te/Operating_System/System_time.htm)
