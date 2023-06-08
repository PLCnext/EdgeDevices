 Quick Reference Guide<br>
 

## Password potect the pre-installed Node-RED for FW 2021.0
<br>

By default, the Node-RED editor is not secured - anyone who can access its IP address can access the editor and deploy changes. <br>

This is only suitable if you are running on a trusted network. <br>

1. Open a new SSH-session (for example using PuTTy). You need to log-in as "Root".  <br> If you already have created a root user before, skip this step and just log in as "Root" <br> 
If you need to create a new "Root" user, use this command: <br>

        sudo passwd root

Write any password you want to give to the root user. The new passwort has to be created twice. <br>

![Node-RED_Passwd2022_Root](../images/Root_Example.png) <br>
    After creating a root user, log-in as root using this command: <BR>

        su

1. This step needs to be written as "Root" user! <br>
Navigate to the folder /opt/plcnext/edge/nodejs/bin and create a new node-red <br> hash-password using this commands: AS ROOT! <br>

        cd /opt/plcnext/edge/nodejs/bin
        ln -s /opt/plcnext/edge/nodejs/bin/node /usr/bin/node
        ln -s /opt/plcnext/edge/nodejs/node-red /usr/bin/node-red
        exit

         
    ![Node-RED_Passwd2022_1](../images/Node-RED_Passwd2022.jpg) <br>

    Now that we linked the correct folders and permissions and logged of the "Root" user, write the following command to link a user-defined password to a hash-password: <br>

        node-red admin hash-pw

    
    As soon as an input mask appears, type a password of your choice into it. <br>
    In my case, I choose "admin" to be the password (not recommended of course): <br>
    
    ![Node-RED_Password2](../images/Node-RED_Passwd2022_3.jpg) <br>
    A new generated "node-red hash-pw" will be generated. <br>
    Copy the hash-pw (long string starting with a $) <br>
     
    
2. In this step, it is required to open a WinSCP session to your EPC. <br>
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