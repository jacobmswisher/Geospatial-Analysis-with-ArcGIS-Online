[<<< Previous](../README.md) | [Next >>>](Part2.md) 

# Part 1: Geospatial Analysis - An Overview

This page provides an overview of geospatial analysis. Here, you can read more about what geospatial analysis is, how geospatial analysis works, and how geospatial analysts approach problem-solving using workflows.

**If you don't want to read through this section now, you can skip ahead to [part 2 of the workshop](Part2.md) and dive right into geospatial analysis in ArcGIS Online.**

## What is Geospatial Analysis?

Geospatial analysis is a multi-step approach to problem-solving that involves the use GIS software to perform operations on spatial data. 

## How does Geospatial Analysis Work?

Take, for example, the following research question related to the topic of energy use along Colorado's Front Range: **how many oil and natural gas wells are within 50 miles of Colorado Springs, Colorado?**

To solve this research problem, a geospatial analyst would begin by gathering data related to the research question. In this case, the analyst would acquire a feature class containing oil and natural gas wells in the state of Colorado as well as a feature class depicting the Colorado Springs city limits (as seen in the map below). By mapping current wells and the city of Colorado Springs, the analyst would be able to **vizualize** where people are extracting oil and natural gas in Colorado in relation to the city of Colorado Springs. But how could the analyst determine how many wells are within 50 miles of Colorado Springs?

<p align="center">
  <img src="https://github.com/jacobmswisher/Geospatial-Analysis-with-ArcGIS-Online/blob/a2fe5a2cc7cad08bc9a262621dca13a9f1a0ad60/Sections/Images/Figure%201.jpg">
</p>

To determine which wells are within 50 miles of Colorado Springs, the analyst would likely create a new feature class that contains a polygon representing the area between the Colorado Springs city limits and a distance of 50 miles from the city limits. To do so, the analyst would use an operation called **create buffers** (a tool you will learn how to use later in this workshop).

<p align="center">
  <img src="https://github.com/jacobmswisher/Geospatial-Analysis-with-ArcGIS-Online/blob/a2fe5a2cc7cad08bc9a262621dca13a9f1a0ad60/Sections/Images/Figure%202.jpg">
</p>

After creating a 50 mile buffer of the Colorado Springs city limits, the analyst could then use an operation called **overlay layers** (another tool covered in this workshop) to create a new feature class containing all of the wells that are located inside the 50-mile buffer.

<p align="center">
  <img src="https://github.com/jacobmswisher/Geospatial-Analysis-with-ArcGIS-Online/blob/a2fe5a2cc7cad08bc9a262621dca13a9f1a0ad60/Sections/Images/Figure%203.jpg">
</p>

Then, the analyst could look at the attribute table for the new feature class and discover that there are currently 2,197 active oil and natural gas wells within 50 miles of Colorado Springs.

## Using Workflows

The process outlined above is what GIS analysts refer to as a **workflow**.

**Workflow - a planned, multi-step sequence that combines data and operations to solve answer a question.**

In this case, the workflow for determining how many wells are within 50 miles of Colorado Springs looked like this:

<p align="center">
  <img src="https://github.com/jacobmswisher/Geospatial-Analysis-with-ArcGIS-Online/blob/cdbba3914a79d389114fd771bf00dfcf37012e3b/Sections/Images/Figure%204.jpg">
</p>

However, another analyst might have decided to solve the problem using an alternative workflow that you will learn how to employ in this workshop:

<p align="center">
  <img src="https://github.com/jacobmswisher/Geospatial-Analysis-with-ArcGIS-Online/blob/a2fe5a2cc7cad08bc9a262621dca13a9f1a0ad60/Sections/Images/Figure%205.jpg">
</p>

One of the goals of this workshop is for you to become proficient with assembling the different tools you will learn how to use into workflows that will allow you to solve problems and answer questions using ArcGIS Online. However, there is not always a **right** workflow for solving a problem. Rather, developing workflows is often about making choices that **feel right to you** in order to effectively combine operations and spatial data to answer a research question.

[<<< Previous](../README.md) | [Next >>>](Part2.md) 
