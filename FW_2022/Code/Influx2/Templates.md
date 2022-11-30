# Quick Reference Guide<br>

## InfluxDB 2.0 Templates

InfluxDB templates are preconfigured InfluxDB resources and can contain everything from dashboards and Telegraf configurations to notifications and alerts.  <br>
<br>
In this example, a Template to monitor the network performance is beeing installed <br>
All other Templates (from Github or self build) should follow the exact same process while installing. <br>
<br>

1. Naviagte to "Settings" --> "Templates".
2. Paste the URL of the Templates resouce. A list of predefined Templates can be find [here](https://github.com/influxdata/community-templates/).<BR>
In this example, the ["Network-Interface-Performance"](https://github.com/influxdata/community-templates/tree/master/network_interface_performance) package will be installed.<br>
3. Paste the URL of the ["Network-Interface-Performance"](https://github.com/influxdata/community-templates/tree/master/network_interface_performance) and "Lookup for Templates". Install all the resources found from Github via the button "Install Template". <br>
![Template_Install](../../images/Templates1.JPG) <br>
4. Next, navigate to "Data" --> "Telegraf" and open the new created "Network Interface Monitoring" Telegraf-Configuration the Template installed. <br>
![Template_Install2](../../images/Templates2.JPG) <br>
5. Change all configurations ("$") according to your system. <br>
![Template_Install3](../../images/Templates3.JPG) <br>
6. Save the Configuration and download it via the button "Download Config". <br>
Open up a new session with "WinSCP" and paste the file into: <br> /opt/plcnext/edge/telegraf/etc/telegraf <br>
![Template_Install4](../../images/Templates4.JPG) <br>

7. To start the Template for the first time, open up a new SSH Shell (PuTTy) and navigate to the folder: <br>

> cd /opt/plcnext/edge/telegraf/usr/bin <br>

Start the application with this command: <br>
> ./telegraf --config /opt/plcnext/edge/telegraf/etc/telegraf/network_interface_monitoring.conf <br>

![Template_Install5](../../images/Templates5.JPG) <br>

Since the Template also installed a new Dashboard, check if the data is received by opening your InfluxDB instance on your EPC and naviagte to "Boards" --> "Network Interface Performance". <br>
In my example, since I am connected to the internet via WIFI, I can see the network traffic via my interface "wlp2s0" very easiliy in just some seconds after deploying the template! <br>

![Template_Install6](../../images/Templates6.JPG) <br>

8. *(Optional)* Autostart of telegraf configuration. <br>
If you want to autostart your telegraf configuration, you have to eiter create a new agent inside the current /etc/init.d/telegraf-init-sh or create a new start-scipt inside the /etc/init.d folder. <br>
![Template_Install7](../../images/Templates7.JPG) <br>
Either way, the script needs to address the new telegraf .config file to autostart the function. <br>
![Template_Install8](../../images/Templates8.JPG) <br>