# Quick Reference Guide<br>

## Backup a whole application and multiply it easily on multiple EPCs

A PLCnext App is stored in a SquashFS container. <br>
A backup of a PLCnext App (for instance your whole Node-RED Programm with all configurations and nodes or InfluxDB with all dashboards) can be easily created to then multiply the pre-configured app to any other EPC. <br>
<br>
The process for backing up and restoring a PLCnext app is always the same, no matter what software the app container contains.  <br>
In this example, the Node-RED app installed on an EPC was fully configured and programmed with nodes. Since this application is to be installed several times on several devices at the end customer, the application is to be rolled out quickly and easily to the other devices without manually exporting each flow. 

## Backup an application (Node-RED) from your EPC

1. To do so, connect to your EPC via SSH (PuTTy). <br>
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

## Install / Restore the Backup-App on another EPC

To install the new created App that you have copied to your Host-PC is as easy as installing any other App you've obtained from the PLCnext Store.

The App (in this example "Node-RED_CHANGE.app) just needs to be installed via the WBM of any PLCnext Controller. <br>
Log-in to the EPC that you want to install the pre-configured App, navigate to "PLCnext Apps" inside the WBM and install and start the app. <br>
![Install_App](/FW_2023/images/Install_App23.jpg) <br> 


Further information about how to create an app container from scratch can also be found inside the [PLCnext Store Info Center](https://store.plcnext.help/st/PLCnext_App_Integration_Guide/PLCnext_Apps/Building_a_PLCnext_App.htm) <br>
