## Quick Reference Guide<br>
### For
## Phoenix Contact: EPC 1522 and EPC 1502
 
### Version: 1.2
---
# InfluxDB Database configuration

InfluxDB is pre-installed on the Edge-PC 15x2. <br>
Data can be administrated, processed or saved locally on the device <br>
Rules can be defined, an alert management can be created. <br>
With Node-RED we can import data from any device in our network, also data from PLCnext Engineer can be imported. <br> To understand how to import data from PLCnext or Node-RED to InfluxDB, please follow the steps on this chapter: <br>
[First Project Example - PLCnext -> Node-RED -> InfluxDB](00_FirstProjectExample.md)

# Create a new database and user
Inside the "InfluxDB Admin" some databases are already set. Those mostly contain system-variables and infromation. Recomended is, to create a new database for variables from the field, so they can be found more easely afterwards.
To do so, click "Create Database" and name your database. Choose a duration, the time how long variables should be stored locally (default unlimited)  <br>
![NewDatabase](images/I_NewDatabase.JPG)
Next, create a new user. Define the username and password and choose the Permission "ALL". <br>
![NewUser](images/I_NewUser.JPG) <br>
Those information have to be inserted in Node-RED when importing variables. For further infromation, stick to the [First Project Example - PLCnext -> Node-RED -> InfluxDB](00_FirstProjectExample.md).

# Creating a visualisation with dashboards
After importing variables to InfluxDB, your variable should be visible in the "EXPLORE" tab in InfluxDB. You can choose data you want to visualise (multiple selection via the "+") and see it's value over the time in the table.
![Explore](images/I_ExploreSm.JPG) <br>
You can also change the visualisation style by clicking the "Visualisation" switch in the top center of the tab. <br>
![VisualisationCh](images/I_VisuCh.JPG) <br>
The generated visualization can now be inserted into a dashboard. <br>
A dashboard can display multiple bars and diagrams. <br>
To do so, click on the upper-right buuton "Send to Dashboard" and eather create a new dashboard or send the diagram to a dashboard you already created. The diagram can be named by choosing a "Cell Name". <br>
![Dashboard](images/I_Dashboards.JPG)

## Working with Template Variables 
You can also create a dashboard with a "Template Variable". That way, you can create dynamic bars and diagrams. This means, you can always change what variable should be visualised over the time in diagrams. <br>
To do so, create a new dashboard in the "DASHBOARD" tab and create a new Template Variable by clicking the upper-right button "+ Add Template Variable" <br>
![TemplateVar](images/I_TemplateVariable.JPG) <br>
Chose "Measurement" as Type and select your database, where your variables are stored - in my case "EdgeDB" (Name of my Database). Give your Template Variable a name under "Name" and click "Create". <br>

Createb new diagrams with different "Visualization" style by adding new cells by clicking the button "Add a new cell to Dashboard" in the upper right corner. <br>
![NewCell](images/I_NewCell.jpg) <br>
This time you don't choose a specific variable to display on the diagram - You have to work with space-holders. This example query can be used to display variables from your database:
>SELECT mean("value") FROM "NAME_OF_YOUR_DATABASE"."autogen".:NAME_OF_YOUR_TEMPLATE_VARIABLE: WHERE time > :dashboardTime: AND time < :upperDashboardTime: AND "location"='INT16' GROUP BY time(:interval:) FILL(null) 

To understand better, my query is displayed:
![TempQuery](images/I_TempQuery.JPG) <br>

In the end, you should be able to change the variable of your diagrams by changing the Template Variable in the upper left corner. <br>
![TempDash](images/I_TempDash.JPG) <br>


# Creating an Alert Management
Open up the tab "ALERTING" -> "Manage Tasks" in InfluxDB. <br>
Create a new alert rule by clicking the button "+ Build Alert Rule"
Define, what variable should create an alert once it reaches an defined value. <br> To do so, define the variable under "Time Series" and define the alert condition under "Conditions". <br>
![NewAlert](images/I_NewAlert.JPG) <br>
Next, we need to define a handler to the alert. You have a huge variaty on what should happen once the alert is active, for example send an e-mail via SMTP. <br>
![AlertHandler](images/I_Handler.JPG) <br>
<BR>
You can also integrate your alerts into your dashboard-visualisation to display, at what time an alert accures. <br>
The alerts can be find in the "EXPLORE" tab in the "chronograf.autogen" database. <br> Next, choose which alert should be visualised and define the "level" to "CRITICAL" so the alert will be displayed. You can then implement the diagram by clicking the button "Send to Dashboard" in the upper-right corner to implement it to your dashbaord.
![AlertExplore](images/AlertExplore.JPG) <br>

