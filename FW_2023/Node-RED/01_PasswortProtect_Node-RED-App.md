### Quick Reference Guide<br>
 

## Password potect your Node-RED App (any version) 
<br>

By default, your Node-RED App from the PLCnext Store is not secured - anyone who can access its IP address and port can access the editor and deploy changes. <br>

This is only suitable if you are running on a trusted network. <br>

To password protect the App follow the the below steps:

1. Open a new SSH-session (for example using PuTTy). <br>
First log-in as "admin" using your credentials, switch to "root" user next. <br>
If you haven't already created a "root" user, enter the following comand and type in a password: <br>
    > sudo passwd root
    ![Node-RED_Passwd2022_Root](/FW_2022/images/Root_Example.png) <br>


2. Log-in as "root". <br>
    > su
    Read the container ID and the App ID using this comand as root: <br>
    > podman ps

    ![Node-REDNode-RED_Protected1](/FW_2023/images/Node-RED_Protected1.jpg) <br>

3. Switch to the App-ID folder. <br>
    Replace "[App-ID]" with the value you have read before.<br>
    > cd /opt/plcnext/appshome/data/[App-ID]/volumes/node-red
    
    Set a new "hash-password". <br>
    Replace "[Container-ID]" with the value you have read before.<br>
    > podman exec -it [Container-ID]  node-red admin hash-pw

    Define and type-in any password you want to configure. <br>
    Copy the newly created hash-password afterwars. <br>

    ![Node-REDNode-RED_Protected2](/FW_2023/images/Node-RED_Protected2.jpg) <br>

4. Open "Win-SCP" next and connect to your EPC as "admin". <br>
    Navigate to the Node-RED folder, which is located at <br>
    /opt/plcnext/appshome/data/[App-ID]/volumes/node-red <br>

    Open the "settings.js" file with a double-click. <br>
    ![Node-REDNode-RED_Protected3](/FW_2023/images/Node-RED_Protected3.jpg) <br>

5.  Inside the file, navigate to the chapter "Securing Node-RED" which is currently commented out. <br>
First delete the command marks "//" and the current hash-pw under "password". <br> 

    ![Node-RED_Password3](/FW_2022/images/Node-RED_Password3.jpg) <br>

    Next, paste your newly created hash-pw from your PuTTy-SSH-Connection as your "password". <br>
![Node-REDNode-RED_Protected4](/FW_2023/images/Node-RED_Protected4.jpg) <br>

6. Safe the "settings.js" file. <br>
If a error-message about insufficient user-rights appears, click on "Skip All", your changes are still implemented. <br>
<br>
Reboot the EPC, for instance yia the WBM. <br>
Connect to your Node-RED App via a Web-Browser. The App should now be password protected with the password you defined before. <br>
<br>
![Node-RED_Password7](/FW_2022/images/Node-RED_Password7.jpg) <br>


