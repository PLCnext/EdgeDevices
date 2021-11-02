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
![VisualisationCh](images/I_VisuCh.jpg) <br>
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

# Example - Use-Case for Template Variables
In this example, data is collected from a machine and then being visualised via multiple Template Variables to be able to visualise different variables in one table. <br>
![TemplateVar](images/Inlfux_Template.jpg) <br>

### Configuration
Create a new dashboard and a the number of Template Variables you require. <br>

### TABLE
To cofigure a table with your tempate variables, create a new cell, defince the "Visualization" as "Table". <br>
Enter the following Query:
>SELECT * FROM "Name_of_your_database"."autogen".:Name_of_your_TempVar: <br>

Add another tab for each template variable. <br>

![TableView](images/TableView.JPG) <br>

Unwanted cells in your table can be configured as "hidden". <br>

![TempVisu](images/tempVisu.jpg) <br>


### Graph

To create a graph using numerous Template variables <br>

> SELECT mean("value") AS "mean_value" FROM "Name_of_your_database"."autogen".:Name_of_your_TempVar: WHERE time > :dashboardTime: AND time < :upperDashboardTime: GROUP BY time(:interval:) FILL(null) 


![TempVisu](images/TemplateGraph.JPG) 
