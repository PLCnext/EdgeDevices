 Quick Reference Guide<br>
 

## Password potect the pre-installed Node-RED for FW 2021.0
<br>

By default, the Node-RED editor is not secured - anyone who can access its IP address can access the editor and deploy changes. <br>

This is only suitable if you are running on a trusted network. <br>

1. Open a new SSH-session (for example using PuTTy). <br>
Navigate to the folder /opt/plcnext/edge/nodejs/bin and create a new node-red hash-password using this commands: <br>


        cd /opt/plcnext/edge/nodejs/bin
        ./node-red admin hash-pw
    
    As soon as an input mask appears, type a password of your choice into it. <br>
    In my case, I choose "admin" to be the password (not recommended of course): <br>
    
    ![Node-RED_Password2](../images/Node-RED_Password2.jpg) <br>

    A new generated "node-red hash-pw" will be generated. <br>
    Copy the has-pw (long string starting with a $) <br>
    
    
2. Open up a new WinSCP Connection. <br>
Open the file "settings.js" inside the EPC /opt/plcnext/.node-red/ <br>
![Node-RED_SettingsFile](../images/Node-RED_Password1.JPG) <br>
Inside the file, navigate to the chapter "Securing Node-RED" which is currently commented out. <br>
![Node-RED_Password3](../images/Node-RED_Password3.jpg) <br>
Delete the comment-marks "//" as shown below, as well as the current hash-password. <br>
Paste the new hash-pw from the SSH-shell before (PuTTy). <br>
![Node-RED_Password4](../images/Node-RED_Password4.jpg) <br>

3. Save the file (settings.js) and close the WinSCP session. <br>
Restart your EPC, for example via the "Restart" button inside the WBM. <br>
After the restart, open up a web-browser and connect to Node-RED (default X3: 192.168.1.10:1880) <br>
A pop-up will appear asking for a log-in. Node-RED is now secured against unauthorized remote access. <br>
![Node-RED_Password7](../images/Node-RED_Password7.jpg) <br>

4. OPTIONAL <br>
We only secured Node-RED (default: Port 1880) against unauthorized access. <br>
If you want to install and use the Node-RED Dashboard UI, that you can install via the Node-RED Palette-Manager (default: Port 1880/ui) as well, you have to secure this access as well. <br>
To do so, the input "httpNodeAuth" inside the file "settings.js" has to be commented out as well. <br>
Enter the username (deafult: "admin"), as well as the node-red hash-pw you created in step 1 and safe the file. <br>
![Node-RED_Password5](../images/Node-RED_Password5.jpg) <br>