### Quick Reference Guide<br>
 

## Password potect your Node-RED App (any version) 
<br>

By default, your Node-RED App from the PLCnext Store is not secured - anyone who can access its IP address and port can access the editor and deploy changes. <br>

This is only suitable if you are running on a trusted network. <br>

To password protect the App follow the below steps:

1. Connect your EPC to the internet. To do so, please follow this chapter: [Connect EPC to internet](/FW_2023/Configuration/02_Network.md). <BR>
2. Install the "node-red-contrib-bcrypt" node using the palette manager. <br>
3. Import the [Password_hash.json](/FW_2023/Node-RED/Examples/010_Password_hash.json) flow. <BR>
4. Update the payload "Password Node" with the password. <BR>
5. Deploy and start the flow. Inject the payload. The hashed value will be in the debug window. <BR>
![Password_Node_Hash](01_PasswordProtect_NR.jpg) <BR>
6. Update "/opt/plcnext/appshome/data/60002172000678/volumes/node-red/settings.js" with the hashed password above. Make sure to uncomment the setting: <BR>
![Password_Node_Hash2](02_PasswordProtect_NR.jpg) <BR>
7. Reboot your device. <BR>
8. Open up your Node-RED editor on your EPC again. You should now see a login required. <BR>
![Password_Node_Hash3](0§_PasswordProtect_NR.jpg) <BR>
8. You can logout by selecting the "preson" icon in the upper right window. <BR>
![Password_Node_Hash4](04_PasswordProtect_NR.jpg) <BR>