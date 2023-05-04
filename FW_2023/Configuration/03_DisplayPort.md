# Quick Reference Guide<br>

## Local Visualisation via DisplayPort

One of the biggest impovements concerns the local DisplayPort of your EPC.<br> Cost-effective HMI solutions can be visualized locally. <br>
The performance of the visualisation overall has improved a lot from FW 2022.0, resource hungry visualizations like Node-RED Dashboard or Grafana can now be output far better. <br>

A DisplayPort Monitor needs to be connected, as well as a USB-mouse and USB-keyboard to your EPC. <br>

>Important!  <br>
Since the DisplayPort Output will only be rescaled during boot-up, please plug in the monitor before powering on the device. <br>

## Configure what should be output as your Home Page
Another big improvement besides the performance is the flexibility of what should be visualised. <br>
You are now able to output any app, software or visualisation that is running local inside your EPC. <br>

To choose what should be output as your "Home Page", connect to your Web Based Management and navigte to "Edge" --> "Dasboard". <br>
![Localhost_Visualisation](/FW_2023/images/Localhost_Visualisation.jpg) <BR>

You can eather set your Homepage to some pre-defined Visualisation like Node-RED ([if you installed the App](/FW_2023/Node-RED/00_Install_Node-RED.md), the WBM or the eHMI if you have a PLCnext Engineer Project running). <br>
If you want to output onther software that you have installed previously, just type in the URL or Port of the App that should be output. <br>
<br>
To give you some examples: <br>
**/daum** (for [Device and Update Management](https://www.plcnextstore.com/permalinks/apps/latest/60002172000527)) <br>
**:53000** (for [Grafana](https://www.plcnextstore.com/permalinks/apps/latest/60002172000509)) <br>
**:1880/ui** (for Node-RED Dashboard) <br>

If your Visualisation or App is running in HTTP instead of HTTPS, you'll need to set the configuration "Use HTTP". <br>

![EPC_DP](/FW_2022/images/EPC_DP.jpg)