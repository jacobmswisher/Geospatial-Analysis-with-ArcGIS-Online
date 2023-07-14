[<<< Previous](Part3.md) | [Next >>>](Part5.md)  

# Part 4: Using Joins

Now that you have learned how use three common operations for working with features in vector datasets, it's time to learn about using joins. Joins will allow you to manipulate attribute tables in vector datasets.

## What are Joins?

A **join** is an operation that appends (joins) information in the attribute table of one dataset (the join dataset) to the attribute table of another dataset (the target dataset).

In ArcGIS Online, you can perform two types of joins:
1. A **table join** - appends information from a **table** (either a standalone table or feature class attribute table) to the attribute table of a **feature class** based on a **relationship between both tables**.
2. A **spatial join** - appends information from the attribute table of one **feature class** to the attribute table of another **feature class** based on a **spatial relationship** between the features in both feature classes.

In this part of the workshop, you will learn how to perform both types of join operations using ArcGIS Online.

## Operation 1: Table Join

Table joins append information from a table (usually in the form of a .csv file) to the attribute table of a target feature class.

Table joins use the following workflow:

<p align="center">
  <img src="https://github.com/jacobmswisher/Geospatial-Analysis-with-ArcGIS-Online/blob/main/Sections/Images/Figure%2032.jpg">
</p>

To join information from the table and feature class, the table join operation relies on the presence of a **key field**.

**Key field - a common field present in the tables of both the target and join datasets.**

For example, analysts often use a common name or id field to join two datasets together. In this example, ID serves as the **key field** to join a list of addresses to a list of grocery stores in South Bend.

<p align="center">
  <img src="https://github.com/jacobmswisher/Geospatial-Analysis-with-ArcGIS-Online/blob/main/Sections/Images/Figure%2033.jpg">
</p>

To see how table joins work in ArcGIS Online, you'll practice by joining the information in Campground Agency Information table to the Campgrounds feature class.

### Step 1: Add Relevant Data to the Map Viewer Classic

Begin by adding the Campground Agency Information table and the Campgrounds feature class to the Map Viewer Classic.

### Step 2: Define Join Parameters in the Analysis Tab

Next, navigate to the join features tool in the summarize data section of the analysis tab.

<p align="center">
  <img src="https://github.com/jacobmswisher/Geospatial-Analysis-with-ArcGIS-Online/blob/main/Sections/Images/Figure%2034.jpg">
</p>

When using the join features tool, you will need to set parameters for:

<table align="center">
  <tr>
    <th>Parameter</th>
    <th>Description</th>
  </tr>
  <tr>
    <td align="center">Target Layer</td>
    <td>The feature class containing the features you want to join new information to.</td>
  </tr>
  <tr>
    <td align="center">Join Layer</td>
    <td>The dataset containing the information to be appended to the target layer. <b>Join layers can be feature layers or tables</b></td>
  </tr>
  <tr>
    <td align="center">Join Settings</td>
    <td>Identifies whether the operation is a <b>table join</b> ("use attribute relationship") or a <b>spatial join</b> ("use spatial relationship").</td>
  </tr>
  <tr>
    <td align="center">Join Operation</td>
    <td>Defines how the the join layer is appended to the target layer.<br><br><b>Join one to one</b> matches each record in the join layer to a single record in the target layer while <b>join one to many</b> matches each record in the join layer to every matching record in the target layer.<br><br><b>Join one to many</b> is commonly used in spatial joins but can be used with table joins too (ex. joining a list of states to campgrounds where each campground has a state id field which means that many campground records would have a common value in the state id field).<br><br><b>Define which record is kept</b> allows you to control the join in cases when multiple records in one layer would be joined to a single record in the the other layer.<br><br><b>Keep all target features</b> allows you to control which features appear in the output feature class. Check this box if you want to keep all features in the target layer even if not all target layer features would recieve appended information via the join layer.</td>
  </tr>
  <tr>
    <td>Join Type</td>
    <td>Allows you to control whether the output layer will include features from the join layer that do not match a record in the target layer attribute table (left join) or if those unmatched features should be discarded (inner join)</td>
  </tr>
  <tr>
    <td align="center">Result Layer Name</td>
    <td>The name of the new feature class containing the joined features.</td>
  </tr>
</table>

To join Campgrounds Agency Information to Campgrounds, configure the parameters for join features so that Campground Agency Information is joined to Campgrounds using a one-to-one table join. In this case, the key field for the table join is the name of each site in Campgrounds. 

<p align="center">
  <img src="https://github.com/jacobmswisher/Geospatial-Analysis-with-ArcGIS-Online/blob/main/Sections/Images/Figure%2035a.jpg">
  <br>
  <img src="https://github.com/jacobmswisher/Geospatial-Analysis-with-ArcGIS-Online/blob/main/Sections/Images/Figure%2035b.jpg">
</p>

### Step 3: Join Campgrounds Agency Information to Campgrounds

After configuring the parameters for the join layers tool, click the run analysis button to join Camground Agency Information to Campgrounds.

### Step 4: Examine the Output Feature Class

After the analysis runs, open up the attribute table for the ouput feature class containing the joined features. In the attribute table, you'll see that each record for an individual site in Campgrounds now has information for which agency (United States Forest Service or Bureau of Land Management) manages the campground.

<p align="center">
  <img src="https://github.com/jacobmswisher/Geospatial-Analysis-with-ArcGIS-Online/blob/main/Sections/Images/Figure%2036.jpg">
</p>

## Practice Scenario 1: Table Joins

Congratulations! You have successfully completed a table join using ArcGIS Online. Time to put your new skills to work in the following practice problem:

Using the Campgrounds feature layer and the 2022 Visitor Data table, create a map that displays federal campgrounds and helps the viewer distinguish which campgrounds are more visited than others.

*Hint: after completing a table join, new options for the output feature layer will appear in the styles tool that will help you to complete this task.*

If needed, view a [sample workflow](https://github.com/jacobmswisher/Geospatial-Analysis-with-ArcGIS-Online/blob/main/Sections/Part6.md#table-join-practice-problem) to solve this problem.

## Operation 2: Spatial Join

Spatial joins append information from the attribute table of one feature class to the attribute table of another feature class.

Spatial joins use the following workflow:

<p align="center">
  <img src="https://github.com/jacobmswisher/Geospatial-Analysis-with-ArcGIS-Online/blob/main/Sections/Images/Figure%2037.jpg">
</p>

To join information from the join feature class to the target feature class, the spatial join operation uses one of the following spatial relationships defined by the user:
<table align="center">
  <tr>
    <th>Spatial Relationship</th>
    <th>Description</th>
  </tr>
  <tr>
    <td align="center">Intersect</td>
    <td>Appends information when a feature in the join feature class <b>overlaps</b> a feature in the target feature class.</td>
  </tr>
  <tr>
    <td align="center">Completely Within</td>
    <td>Appends information when a feature in the target feature class is <b>completely inside</b> the geometry of a feature in the join feature class.</td>
  </tr>
  <tr>
    <td align="center">Within a Distance Of</td>
    <td>Appends information when a feature in the target feature class is <b>within a defined distance</b> of a feature in the join feature class.</td>
  </tr>
</table>

For example, an analyst could identify all federal campgrounds in Montana by joining a feature class with state of Montana to a feature class containing all federal campgrounds. Doing so would attach the information from the feature representing Montana to all features in Campgrounds that have a spatial relationship of being completely within the feature representing Montana.

<p align="center">
  <img src="https://github.com/jacobmswisher/Geospatial-Analysis-with-ArcGIS-Online/blob/main/Sections/Images/Figure%2038.jpg">
</p>

In this case, the join features tool would use a spatial relationship to append the information for the feature representing Montana to **every** point feature in the campgrounds feature class that intersects with the feature representing Montana. The result would allow the analyst to create a map showing which campgrounds are in Montana.

<p align="center">
  <img src="https://github.com/jacobmswisher/Geospatial-Analysis-with-ArcGIS-Online/blob/main/Sections/Images/Figure%2039.jpg">
</p>

To see how spatial joins work in ArcGIS Online, you'll practice by joining the State Boundaries feature class to the Campgrounds feature class.

### Step 1: Add Relevant Data to the Map Viewer Classic

Begin by adding State Boundaries and Campgrounds to the Map Viewer Classic.

### Step 2: Define Join Parameters in the Analysis Tab

Next, navigate to the join features tool and configure the parameters in order to join State Boundaries to Campgrounds.

In contrast to the parameters for performing a **table join**, you will need to make two important changes to perform a **spatial join**:
1. Set the join type to "choose a spatial relationship."
2. Change to join operation from join one to one to join one to many.
   - Leaving the join operation as join one to one would append the information for each feature in the join layer (State Boundaries) to **the first feature** in the target layer (Campgrounds) that meets the criteria of the defined spatial relationship and is first in the defined ranking criteria. In contrast, performing a one to many join will append information for each feature in the join layer (State Boundaries) to **every feature** in the target layer (Campgrounds) that meet the criteria of the defined spatial relationship.

To join State Boundaries to Campgrounds, configure the parameters for join features so that State Boundaires is joined to Campgrounds using a one-to-many spatial join. In this case, the spatial join subtype will need to be set to capture any campgrounds within each state (meaning you can choose intersect or completely within because no points exist on state borders). **Additionally, be sure to zoom out on the map viewer or uncheck the current map extent option at the bottom of the tool pane.**

<p align="center">
  <img src="https://github.com/jacobmswisher/Geospatial-Analysis-with-ArcGIS-Online/blob/main/Sections/Images/Figure%2040a.jpg">
  <br>
  <img src="https://github.com/jacobmswisher/Geospatial-Analysis-with-ArcGIS-Online/blob/main/Sections/Images/Figure%2040b.jpg">
</p>

### Step 3: Join State Boundaries to Campgrounds

After configuring the parameters for the join layers tool, click the run analysis button to join State Boundaries to Campgrounds.

### Step 4: Examine the Output Feature Class

To examine the results of the spatial join, open up the attribute table for the output feature class which should now include fields for the name of each state where each campground is located.

You can also see how your data has changed by adjusting the style of the ouput feature class to symbolize campgrounds according to the state they are in.

<p align="center">
  <img src="https://github.com/jacobmswisher/Geospatial-Analysis-with-ArcGIS-Online/blob/main/Sections/Images/Figure%2041.jpg">
</p>

## Practice Scenario 2: Spatial Joins

Congratulations! You have successfully completed a spatial join using ArcGIS Online. Time to put your new skills to work in the following practice problem:

Using the Campgrounds feature layer and the Administrative Forest Boundaries feature layer, create a map that displays all federal campgrounds and helps the viewer identify which United States Forest Service Region each campground is located in.

If needed, view a [sample workflow](https://github.com/jacobmswisher/Geospatial-Analysis-with-ArcGIS-Online/blob/main/Sections/Part6.md#spatial-join-practice-problem) to solve this problem.

[<<< Previous](Part3.md) | [Next >>>](Part5.md)  
