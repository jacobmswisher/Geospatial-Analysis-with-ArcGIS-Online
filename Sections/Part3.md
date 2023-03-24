[<<< Previous](Part2.md) | [Next >>>](Part4.md)  

# Part 3: Operations for Working with Vector Data

Now that you have learned about how geospatial analysis works and imported all of the data for this workshop into ArcGIS Online, it's time to familiarize yourself with a few commonly used operations for working with vector data ([head here for a refresher on spatial data types](https://github.com/jacobmswisher/Mapping-with-ArcGIS-Online/blob/main/Sections/Part1.md)).

In this section, you will learn how to use three common operations available with ArcGIS Online:
1. Create Buffers
2. Extract Data
3. Overlay Layers

## Operation 1: Create Buffers

The create buffers tool creates a feature class composed of polygons that represent the area between features in an input feature layer and a distance defined by the user. You can create buffers for feature classes with point, line, and polygon geometry.

Create buffers uses the following workflow:

<p align="center">
  <img src="https://github.com/jacobmswisher/Geospatial-Analysis-with-ArcGIS-Online/blob/8cd6a442111a86199cf3dc34edaacfdfb3c47604/Sections/Images/Figure%207.jpg">
</p>

To learn more about how create buffers works, you'll practice by creating a buffer from the South Bend feature class.

### Step 1: Add Relevant Data to the Map Viewer Classic

In this exercise, you are going to create a 100-mile buffer from a point representing the city of South Bend, Indiana.

To get started, begin by adding the South Bend feature class to a new map using the add layer tool in Map Viewer Classic.

<p align="center">
  <img src="https://github.com/jacobmswisher/Geospatial-Analysis-with-ArcGIS-Online/blob/8cd6a442111a86199cf3dc34edaacfdfb3c47604/Sections/Images/Figure%208.jpg">
</p>

### Step 2: Define Buffer Parameters in the Analysis Tab

You can access create buffers and other operations for geospatial analysis in the analysis tab of the Map View Classic. Begin by clicking on the analysis tab.

<p align="center">
  <img src="https://github.com/jacobmswisher/Geospatial-Analysis-with-ArcGIS-Online/blob/637f9d324c474b02c48eaf494540a5ee94fe127c/Sections/Images/Figure%209.jpg">
</p>

Then, navigate to the use proximity section of the analysis tab and select create buffers.

<p align="center">
  <img src="https://github.com/jacobmswisher/Geospatial-Analysis-with-ArcGIS-Online/blob/8540f5d64c8a4a4efe4d77d47f27a4a2ece54aa9/Sections/Images/Figure%2010.jpg">
</p>

Whenever you use an analysis tool to perform an operation in ArcGIS Online, the platform will ask you to define a series of **parameters** that provide ArcGIS Online with instructions for the operation.

**Parameter - a specified condition that dictates how an operation is performed.**

ArcGIS Online will ask you to define parameters in a series of steps laid out in a pane on the left-hand side of your browser. For example, the options to set parameters for the create buffers tool look like this:

<p align="center">
  <img src="https://github.com/jacobmswisher/Geospatial-Analysis-with-ArcGIS-Online/blob/8540f5d64c8a4a4efe4d77d47f27a4a2ece54aa9/Sections/Images/Figure%2011.jpg">
</p>

In the case of the create buffers tool, you will need to set parameters for:

<table align="center">
  <tr>
    <th>Parameter</th>
    <th>Description</th>
  </tr>
  <tr>
    <td align="center">Input Layer</td>
    <td align="center">The feature class from which ArcGIS Online will create the buffers.</td>
  </tr>
  <tr>
    <td align="center">Buffer Size</td>
    <td align="center">The distance that will be used to measure the space in between the features in the input layer the outer edge of each buffer.</td>
  </tr>
  <tr>
    <td align="center">Output (Result) Layer Name</td>
    <td align="center">The name of the new feature class containing polygons representing the buffers.</td>
  </tr>
</table>

**Note: Some tools include optional parameters. In this case, ArcGIS Online provides you an option to control the geometry of output features when creating a buffer from a feature class with point geometry. Selecting overlap (the default) creates a separate buffer for each input feature while selecting dissolve creates a multipart feature that dissolves separte buffers into a single polygon. When in doubt, the blue info circle can help you determine how selecting specific options will change the output from an operation.**

Adjust the parameters for the create buffers tool as needed to instruct ArcGIS Online to create a 100-mile buffer around the point representing the city of South Bend.

<p align="center">
  <img src="https://github.com/jacobmswisher/Geospatial-Analysis-with-ArcGIS-Online/blob/8540f5d64c8a4a4efe4d77d47f27a4a2ece54aa9/Sections/Images/Figure%2012.jpg">
</p>

**Note: When buffering a feature class with polygon geometry, you also have access to the include and exclude options. Selecting exclude is helpful when you want to create a buffer that does not contain the area of an input feature.**

<p align="center">
  <img src="https://github.com/jacobmswisher/Geospatial-Analysis-with-ArcGIS-Online/blob/8cd6a442111a86199cf3dc34edaacfdfb3c47604/Sections/Images/Figure%2013.jpg">
</p>

### Step 3: Buffer

After defining the parameters to create the 100-mile buffer from the South Bend feature class, click the run analysis button.

<p align="center">
  <img src="https://github.com/jacobmswisher/Geospatial-Analysis-with-ArcGIS-Online/blob/8540f5d64c8a4a4efe4d77d47f27a4a2ece54aa9/Sections/Images/Figure%2014.jpg">
</p>

### Step 4: Examine the Output Feature Class

Once ArcGIS Online has finished creating a buffer from the input feature class, the platform will immediately display the output feature class in the Map Viewer Classic. From here, you can view the buffer, look at the attribute table, or perform additional operations using the output layer in the analysis tab.

<p align="center">
  <img src="https://github.com/jacobmswisher/Geospatial-Analysis-with-ArcGIS-Online/blob/8cd6a442111a86199cf3dc34edaacfdfb3c47604/Sections/Images/Figure%2015.jpg">
</p>

## Operation 2: Extract Data

Extract data is a tool that allows users to extract a subset of features from an input feature class and create a new output of those extracted features. 

In this section, you will learn how to exract data using two methods:
1. By extracting features based on information in the attribute table with the help of the filters tool
2. By extracting features based on a spatial relationship between the input feature class and a second feature class

## Method 1: Extract Data with Filters

Extracting data with the help of the filters tool uses the following workflow:

<p align="center">
  <img src="https://github.com/jacobmswisher/Geospatial-Analysis-with-ArcGIS-Online/blob/8cd6a442111a86199cf3dc34edaacfdfb3c47604/Sections/Images/Figure%2016.jpg">
</p>

To learn more about how extract data works with filters, you'll practice by creating a feature class with a single representing the state of Indiana from the State_Boundaries feature class.

### Step 1: Add Relevant Data to Map Viewer Classic

To get started, begin by adding the State_Boundaries feature class to the Map Viewer Classic.

### Step 2: Apply Filter to Input Feature Class

When using filters to create a new feature class with extract data you will need to apply a filter to your input feature class with criteria to select all of the feature you want to appear in the output feature class after running the extract data tool.

In this case, we'll apply a filter to select the state of Indiana from the State_Boundaries feature class. You can access filters via the content tab in Map Viewer Classic.

<p align="center">
  <img src="https://github.com/jacobmswisher/Geospatial-Analysis-with-ArcGIS-Online/blob/8cd6a442111a86199cf3dc34edaacfdfb3c47604/Sections/Images/Figure%2017.jpg">
</p>

Configure a filter that will select Indiana from the State_Boundaries feature class. Then, apply the filter.

**If you need a refresher on how filters work in ArcGIS Online, head [here](https://github.com/jacobmswisher/Mapping-with-ArcGIS-Online/blob/main/Sections/Part5.md)**

<p align="center">
  <img src="https://github.com/jacobmswisher/Geospatial-Analysis-with-ArcGIS-Online/blob/8540f5d64c8a4a4efe4d77d47f27a4a2ece54aa9/Sections/Images/Figure%2018.jpg">
</p>

After filtering State_Boundaries for Indiana, your map viewer should look like this:

<p align="center">
  <img src="https://github.com/jacobmswisher/Geospatial-Analysis-with-ArcGIS-Online/blob/8cd6a442111a86199cf3dc34edaacfdfb3c47604/Sections/Images/Figure%2019.jpg">
</p>

### Step 3: Set Parameters for Extract Data Tool

Now that you have filtered State_Boundaries to select the feature representing Indiana, head to the analysis tab and select the extract data tool under the manage data section of the tab.

<p align="center">
  <img src="https://github.com/jacobmswisher/Geospatial-Analysis-with-ArcGIS-Online/blob/8540f5d64c8a4a4efe4d77d47f27a4a2ece54aa9/Sections/Images/Figure%2020.jpg">
</p>

To use extract data, you will need to set parameters for:

<table align="center">
  <tr>
    <th>Parameter</th>
    <th>Description</th>
  </tr>
  <tr>
    <td align="center">Input Layer</td>
    <td>This is the layer that contains the features you want to extract.</td>
  </tr>
  <tr>
    <td align="center">Study Area</td>
    <td>Extract data will only extract features within the study area.<br>*When using the filters method set the study area to be the same as the input layer.<br><b>Note: you will almost always use the select features setting in defining the study area parameters (more on clip features below in the Overlay Layers section of the  workshop).<b></td>
  </tr>
  <tr>
    <td align="center">Output Data Format</td>
    <td>This allows you to control the file format of the output containing the extracted features.</td>
  </tr>
  <tr>
    <td align="center">Output (Result) File Name</td>
    <td>The name of the new file containing the extracted features.</td>
  </tr>
</table>

To create a feature class containing the state of Indiana, adjust the parameters for the extract data tool to instruct ArcGIS Online to extract all features from State_Boundaries that are within a study area defined by State_Boundaries. Output the new feature class in the format of a shapefile.

<p align="center">
  <img src="https://github.com/jacobmswisher/Geospatial-Analysis-with-ArcGIS-Online/blob/8540f5d64c8a4a4efe4d77d47f27a4a2ece54aa9/Sections/Images/Figure%2021.jpg">
</p>

### Step 4: Extract Data

After defining the parameters to extract Indiana from the State_Boundaries feature class, click the run analysis button.

<p align="center">
  <img src="https://github.com/jacobmswisher/Geospatial-Analysis-with-ArcGIS-Online/blob/8540f5d64c8a4a4efe4d77d47f27a4a2ece54aa9/Sections/Images/Figure%2022.jpg">
</p>

### Step 5: Upload Output Feature Class to ArcGIS Online

After the analysis runs, ArcGIS Online will save the output feature class as a shapefile in the content tab. However, using extract data does not automatically host the new shapefile as a feature layer in ArcGIS Online (unlike with the create buffers tool).

In order to work with your output feature class, you will need to download the shapefile and then create a new feature layer in the content tab.

Begin by finding the output feature class in your content tab and downloading the shapefile by clicking on the three-dot button on the right-hand side of the item.

<p align="center">
  <img src="https://github.com/jacobmswisher/Geospatial-Analysis-with-ArcGIS-Online/blob/8cd6a442111a86199cf3dc34edaacfdfb3c47604/Sections/Images/Figure%2023.jpg">
</p>

Then, create a new feature layer using the downloaded shapefile.

**Note: Because the shapefile already exists in the content tab, you will need to rename the downloaded file before using it to create a new feature layer in ArcGIS Online.**

### Step 6: View Output Feature Class

After creating a new feature layer from the downloaded shapefile, add the new feature layer to the Map Viewer to examine and work with your extracted data.

<p align="center">
  <img src="https://github.com/jacobmswisher/Geospatial-Analysis-with-ArcGIS-Online/blob/8cd6a442111a86199cf3dc34edaacfdfb3c47604/Sections/Images/Figure%2024.jpg">
</p>

## Method 2: Extract Data with Spatial Relationships

Extract data can also be used to extract features from an input feature class based on a spatial relationship defined via parameters.

Extracting data through a spatial relationship uses the following workflow:

<p align="center">
  <img src="https://github.com/jacobmswisher/Geospatial-Analysis-with-ArcGIS-Online/blob/8cd6a442111a86199cf3dc34edaacfdfb3c47604/Sections/Images/Figure%2025.jpg">
</p>

To learn how to extract data using spatial relationships, we will use the 100-mile buffer from earlier in the workshop to create a feature class of states that are within 100 miles of South Bend.

### Step 1: Add Relevant Data to Map Viewer Classic

To get started, add State_Boundaries and the 100-mile buffer of South Bend feature classes to the Map View Classic.

### Step 2: Set Parameters for Extract Data Tool

Then, navigate to the extract data tool in the analysis tab. When extracting data based on spatial relationships, the only step in defining the parameters for the extract data tool that differs from the filters method is **Step 2: Define the Study Area**.

In this case, we want to extract the states from State_Boundaries that are within 100 miles of South Bend. Therefore, the "Study Area" for this operation needs to be a feature representing the area for a 100 mile buffer from South Bend (just like the one you created earlier!).

Adjust the parameters for the extract data tool as needed to create a new feature class containing the states that are within 100 miles of South Bend.

<p align="center">
  <img src="https://github.com/jacobmswisher/Geospatial-Analysis-with-ArcGIS-Online/blob/8540f5d64c8a4a4efe4d77d47f27a4a2ece54aa9/Sections/Images/Figure%2026.jpg">
</p>

**Note: Employ the select features option here. Using clip features will extract *only* the portions of the states that are within the buffer area rather than extracting the entire feature representing each state. In the remainder of the workshop, you will learn how to accomplish this task using the Overlay Layers tool which is the preferred method for this operation.**

### Step 3: Extract Data

Once you have configured the paramaters for the extract data tool, click the run analysis button.

### Step 4: Upload Output Feature Class to ArcGIS Online

Then, download the extracted shapefile and upload the output feature class as a new feature layer in ArcGIS Online

### Step 5: View Output Feature Class

Finally, take a look at your output layer in the map view. You will notice that ArcGIS Online has identified all states within the buffer area, even if the only are barely within 100 miles of South Bend as in the case of Wisconsin.

<p align="center">
  <img src="https://github.com/jacobmswisher/Geospatial-Analysis-with-ArcGIS-Online/blob/8cd6a442111a86199cf3dc34edaacfdfb3c47604/Sections/Images/Figure%2027.jpg">
</p>

## Operation 3: Overlay Layers

Overlay layers is a tool that allows users to create a new feature class based on a defined relationship (interesect, erase, or union) between an input layer and an overlay layer. 

Overlay Layers uses the following workflow:

<p align="center">
  <img src="https://github.com/jacobmswisher/Geospatial-Analysis-with-ArcGIS-Online/blob/8cd6a442111a86199cf3dc34edaacfdfb3c47604/Sections/Images/Figure%2028.jpg">
</p>

In this section, you'll learn how to use overlay layers to create a feature representing the portion of Indiana that is within 100 miles of South Bend.

**Note: Although you will learn how to use overlay layers using feature classes with polygon geometry, overlay layers works with feature classes with point, line, or polygon geometry.**

### Step 1: Add Relevant Data to Map Viewer Classic

To get started, add the feature classes you created representing Indiana and the 100-mile buffer of South Bend feature classes to the Map View Classic.

### Step 2: Set Parameters for Overlay Layers Tool

Then, navigate to the overlay layers tool in the analysis tab. 

<p align="center">
  <img src="https://github.com/jacobmswisher/Geospatial-Analysis-with-ArcGIS-Online/blob/8540f5d64c8a4a4efe4d77d47f27a4a2ece54aa9/Sections/Images/Figure%2029.jpg">
</p>

To use overlay layers, you will need to set parameters for:

<table align="center">
  <tr>
    <th>Parameter</th>
    <th>Description</th>
  </tr>
  <tr>
    <td align="center">Input Layer</td>
    <td>This is the layer that contains the features you want to create a new feature class from.</td>
  </tr>
  <tr>
    <td align="center">Overlay Layer</td>
    <td>This is the layer that provides the feautres used to determine what happens to overlapping features from the input layer based on the overlay method.</td>
  </tr>
  <tr>
    <td align="center"><Overlay Method/td>
    <td>Defines how features in the intput layer are transformed.<br>There are three overlay methods available in ArcGIS Online:<br>1. Intersect: creates a layer containing only features (or portions of features) that overlap with the overlay layer.<br>2. Erase: creates a layer containing only features (or portions of features) that <b>do not<b> overlap with the overlay layer.<br>3. Union: Creates a layer containing features that are combinations of overlapping features in the input and overlay layers.</td>
  </tr>
  <tr>
    <td align="center">Output (Result) Layer Name</td>
    <td>the name of the new feature layer containing the features created through the overlay.</td>
  </tr>
</table>

Configure the parameters in order to create a polygon representing the part of Indiana that is within 100 miles of South Bend. If you need help selecting the correct parameters, consult the image below.

*Check for understanding: can you explain why you used intersect instead of erase or union?*

<p align="center">
  <img src="https://github.com/jacobmswisher/Geospatial-Analysis-with-ArcGIS-Online/blob/8540f5d64c8a4a4efe4d77d47f27a4a2ece54aa9/Sections/Images/Figure%2030.jpg">
</p>

### Step 3: Overlay Layers

Once you have configured the paramaters for the overlay layers tool, click the run analysis button.

### Step 4: View Output Feature Class

After running the analysis, ArcGIS Online will immediately add the output feature class to the Map Viewer Classic as a hosted feature layer.

Your output should look like this:

<p align="center">
  <img src="https://github.com/jacobmswisher/Geospatial-Analysis-with-ArcGIS-Online/blob/8cd6a442111a86199cf3dc34edaacfdfb3c47604/Sections/Images/Figure%2031.jpg">
</p>

**Note: You can create this output using the clip features setting in the extract data tool. However, using the overlay layers tool saves time as you do not have to download an output shapefile and manually create a new feature layer.**

## Practice Scenario

Congratulations! You now know how to use three core operations that are part of the geospatial analyst's toolkit. Time to put your new skills into practice!

**Problem:** Using the Campgrounds and National_Park_Boundaries feature layers that you created during Part 2: Data Preperation, determine how many campgrounds are within 50 miles of Yellowstone National Park.

*Hint: The attribute table can help you to quickly determine the number of features in a feature class.*

[<<< Previous](Part2.md) | [Next >>>](Part4.md)  
