# Quick Reference Guide<br>

## InfluxDB 2.0 Templates

1. Naviagte to "Settings" --> "Templates".
2. Paste the URL of the Templates resouce. A list of predefined Templates can be find [here](https://github.com/influxdata/community-templates/).<BR>
In this example, the ["Network-Interface-Performance"](https://github.com/influxdata/community-templates/tree/master/network_interface_performance) package will be installed.<br>
3. Paste the URL of the ["Network-Interface-Performance"](https://github.com/influxdata/community-templates/tree/master/network_interface_performance) and "Lookup for Templates". Install all the resources found from Github by "Install Template". <bt>
![Template_Install](../../images/Templates1.JPG) <br>
4. Next, navigate to "Data" --> "Telegraf" and open the new created "Network Interface Monitoring" Configuration the Template installed. <br>
![Template_Install2](../../images/Templates2.JPG) <br>
5. Change all configuartion ("$") according to your system. <br>
![Template_Install3](../../images/Templates3.JPG) <br>
6. Save the Configuration and download it via the button "Donload Config". <br>
Open up a new session with "WinSCP" and navigate to paste the folder into: <br> /opt/plcnext/edge/telegraf/etc/telegraf <br>
![Template_Install4](../../images/Templates4.JPG) <br>

7. To start the Template for the first time, open up a new SSH Shell (PuTTy) and navigate to the folder: <br>

> cd /opt/plcnext/edge/telegraf/usr/bin <br>

Start the application with this command: <br>
> ./telegraf --config /opt/plcnext/edge/telegraf/etc/telegraf/network_interface_monitoring.conf <br>

![Template_Install5](../../images/Templates5.JPG) <br>

Since the Template also installed a new Dasboard, check if the data is received by opening your InfluxDB instance on your EPC and naviagte to "Boards" --> "Network Interface Performance". <br>
In my example, since I am connected to the internet via WIFI, I can see the network traffic via my interace "wlp2s0" very easiliy in just some seconds after deploying the template! <br>

![Template_Install6](../../images/Templates6.JPG) <br>