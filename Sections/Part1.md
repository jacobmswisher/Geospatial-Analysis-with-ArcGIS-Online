[<<< Previous](../README.md) | [Next >>>](Part2.md) 

# Part 1: Geospatial Analysis - An Overview

This page provides an overview of geospatial analysis, the topic of this workshop. Here, you can read more about what geospatial analysis is, how geospatial analysis works, and how geospatial analysts like you approach problem-solving using workflows.

**If you don't want to read through this section now, you can skip ahead to [part 2 of the workshop](Part2.md) and dive right into geospatial analysis using ArcGIS Online.**

## What is Geospatial Analysis?

Geospatial analysis is a multi-step approach to problem-solving where researchers use GIS software to perform operations on spatial data. 

The use of computational operations to create or transform spatial data distinguishes geospatial analysis from mapping (the practice of creating/acquiring and visualizing spatial data).

## How does Geospatial Analysis Work?

Take, for example, the following research question related to the topic of energy use along Colorado's Front Range: **how many oil and natural gas wells are within 50 miles of Colorado Springs, Colorado?**

To solve this research problem, a geospatial analyst would begin by gathering data related to the research question. In this case, the analyst would acquire a feature class containing oil and natural gas wells in the state of Colorado as well as a feature class depicting the Colorado Springs city limits. By mapping current wells and the city of Colorado Springs, the analyst would be able to vizualize where people are extracting oil and natural gas in Colorado in relation to the city of Colorado Springs. But how could the analyst tell which wells are within 50 miles of Colorado Springs?

**Figure 1**
<p align="center">
  <img src="">
</p>

To determine which wells are within 50 miles of Colorado Springs, the analyst would create a new feature class that contains a polygon representing the area between the Colorado Springs city limits and a distance of 50 miles from the city limits. To do so, the analyst would use an operation called **buffer** (a tool you will learn how to use later in this workshop).

**Figure 2**
<p align="center">
  <img src="">
</p>

After creating a 50 mile buffer of the Colorado Springs city limits, the analyst could then use an operation called **overlay layers** (another tool covered in this workshop) to create a new feature class containing all of the wells that are located inside the 50 mile buffer.

**Figure 3**
<p align="center">
  <img src="">
</p>

Then, the analyst could look at the attribute table for the new feature class and quickly determine that there are currently 2,197 active wells within 50 miles of Colorado Springs.

## Using Workflows

The process outlined above is what GIS analysts refer to as a **workflow**.

**Workflow - a planned, multistep sequence that combines data and operations to solve answer a question.**

In this case, the workflow for determining how many wells are within 50 miles of Colorado Springs looked like this:

**Figure 4**
<p align="center">
  <img src="">
</p>

However, another analyst might have solved the problem using an alternative workflow, such as this one:

**Figure 5**
<p align="center">
  <img src="">
</p>

One of the goals of this workshop is for you to become proficient with assembling the different tools you will learn how to use in the following sections into workflows that will allow you to solve problems and answer questions using ArcGIS Online. However, there is not always a *right* workflow to solve a problem. Rather, developing workflows is about making choices that feel right to you in order to effectively combine operations and spatial data to answer a research questions.

[<<< Previous](../README.md) | [Next >>>](Part2.md) 
