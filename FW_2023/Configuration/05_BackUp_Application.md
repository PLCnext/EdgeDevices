# Quick Reference Guide<br>

## Backup a whole application and multiply it easily on multiple EPCs

>Note: The first 3 steps are similar to the last guide [>How to backup a running App<](/FW_2023/Configuration/04_BackUp_App_Container.md) <BR>

1. First we need to import each individual App from the EPC via SSH (PuTTy). <br>
Navigate into the folder /opt/plcnext/appshome/data <br>
In there, all installed apps with their App-IDs can be found.<br>
If several apps are installed, the app ID can be found in the WBM under "PLCnext Apps" with the respective software. <br>
![Backup_Restore_App_IDs](/FW_2023/images/Backup_app1.JPG) <br>

2. The app can now be restored into a new app container via the command <br>

        plcnextapp create <app_id> <Name_of_new_AppContainer>

    ![Backup_Restore_Command](/FW_2023/images/Backup_app2.JPG) <br>

3. The new created app, in the above example "NodeRED_CHANGE.app" was now created inside the same folder. <br>
This app can now be copied to your Host-PC, for example via "WinSCP". <br>
![Backup_Restore_App_Copy](/FW_2023/images/Backup_app3.JPG) <br>
In this example, I created a new app "Node-RED Change" and "InfluxDB Change" that I want to deploy to another EPC. The same procedure needs to be done with any other PLCnext app. <br>

4. Copy the new created apps to your Host-PC via WinSCP. <br>
Next, dezip the .app folders, for example via the 7zip tool on your Host-PC. <br>
![Dezipped](/FW_2023/images/Dezipped2.jpg)<br>

>Note: While the diraction doesn't matter, always use one app (in this case Node-RED) as the "base" and copy all files and configure only in your base-app.
<BR>
5. Some contents of one dezipped folder needs to be copied into the other one. <br> In this example, I will copy files from the InfluxDB app into the Node-RED app:
Copy the ".tar.gz" file under "images" into the other app folder in same location. <br>
![CopyImage1](/FW_2023/images/Backup_application1.jpg) <br>
Next, copy the files from the "volumes" folder from the one app to the other one, also into the "volumes" folder. <BR>
![CopyImage8](/FW_2023/images/Backup_application8.jpg) <br>


6. Next, the "docker-compose.yml" file needs to be configured. <BR>
![CopyImage2](/FW_2023/images/Backup_application2.jpg) <br>
Just copy the content from the docker-compose.yml from the one app (in this case InfluxDB) into the other app and save the file. <br>
It should look like this: <br>

![CopyImage3](/FW_2023/images/Backup_application3.jpg) <br>

7. This is all you need to do, to combine both apps into one solution to share! <br>
You can change the name and the identifier of your new app in the "app_info.json" file. <BR>
![CopyImage4](/FW_2023/images/Backup_application4.jpg) <br>

## Deploy your new created app to another EPC. <BR>

1. Paste the new app including the changed files into the EPC via WinSCP. <br>
![CopyImage5](/FW_2023/images/Backup_application5.jpg) <br>

2. Create the app container using this command via Putty: <BR>
![CopyImage6](/FW_2023/images/Backup_application6.jpg) <br>
A new app container ".app" will be build. Either install the app container via command or import the .app file and install the file via the WBM of the EPC. <BR>
To share this app top several EPCs, the steps before are not needed anymore, simply install the new App-Container via the WBM. <BR>

3. Thanks to the easy PLCnext App handling, enjoy deploying your running application with as many single software components to as many EPCs you are running in your plant! <br>
![CopyImage7](/FW_2023/images/Backup_application7.jpg) <br>
The .app file can also easily be send to collegues or why not share your new app inside the PLCnext Store. :) <br>

Once started, open the ports of each individial part of your new app, everything 