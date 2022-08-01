# Module 14 Class 2: Creating Tableau Charts, Dashboards, and Stories

## Overview

Before class, walk through this week's Challenge assignment in office hours. In class, the students will delve further into Tableau to create area and bubble charts; then, they’ll learn how to create a Tableau dashboard and story. 

## Learning Objectives

By the end of class, students will be able to:

* Create area and bubble charts
* Create Tableau dashboards
* Create Tableau stories

- - -

## Instructor Notes

The activities in this class will complement Lessons **14.3.4: Find the Average Trip Duration by Age** through **14.5.1: Introduction to Tableau Stories**. The students will benefit from these activities if they‘ve progressed through these lessons, which cover the following concepts, techniques, and tasks:  

  * Change the aggregation on a measure datatype 
  * Change the visualization to area chart
  * Convert a field from a measure to a dimension
  * Filter data in a visualization
  * Create a Tableau dashboard
  * Create a Tableau story

* If you have issues with any of today's activities, you may report it [here](http://tiny.cc/BootCampFeedback).

## Slides

[Tableau Day 2 slideshow](https://docs.google.com/presentation/d/1IWcl3kqTb7bIl4rMB3Q6pFu3d-yz7X24-wI0qWJrz2w/edit?usp=sharing)

## Student Resources

If students were unable to download today's [activity resources](https://2u-data-curriculum-team.s3.amazonaws.com/data-viz-online-lesson-plans/14-Lessons/14-2-Student_Resources.zip) from Canvas, please share them with the students.

- - - 

## Before Class

### 0. Office Hours

| Activity Time: 0:30       |  Elapsed Time:     -0:30  |
|---------------------------|---------------------------|

<details>
  <summary><strong>📣 Instructor Do: Challenge Instruction Walkthrough</strong></summary>

Let the students know that the first few minutes of Office Hours will include a walkthrough of the Challenge requirements and rubric, as well as helpful tips they need in order to be successful.

Open the Challenge in Canvas and go through the high-level instructions and requirements with your class. Be sure to check for understanding.

Open the Rubric in Canvas, go through the Mastery column with your class, and show how it maps back to the requirements for each deliverable. Be sure to check for understanding.

The first part of the assignment, **Deliverable 1: Change Trip Duration to a Datetime Format**, requires them to use Pandas to change the datatype of the "tripduration" column from integer to datetime.

We have provided a [starter code](../../../01-Assignments/14-NYC-Citi-Bikes/Resources/NYC_CitiBike_Challenge_starter_code.ipynb) to help them get started.

Some students will try to convert the datatype in Tableau. This conversion will not create the elapsed time in hours and minutes that is needed for Deliverable 2. Some may try to use the calculated field option, but we advise against this today because we’d like them to practice using their data engineering skills instead. Others might be familiar with using the `astype()` function to change a datatype. However, for this part of the Challenge, the learners will need to use the `pandas.to_datetime()` function. 

Also, using Tableau instead of Pandas to change the datatype of the "tripduration" column to "Date and Time" will not produce the same visualizations in Deliverable 2. Trying to change the datatype by creating a calculated field may take more time for the less experienced Tableau user than the steps in Deliverable 1.

We have provided a GoogleFu tip and a short exercise in the **Hint** callout to help the learners convert a datatype from integer to datetime. It is important that they use the right unit of time in the `unit=` parameter.  

They have the option of converting the "tripduration" column or creating a new column with the converted datetime datatype. 

Once they convert the "tripduration" column datatype, they'll need to export the DataFrame as a CSV file. This file will be used in Deliverable 2. 

For the second part of the assignment, **Deliverable 2: Create Visualizations for the Trip Analysis**, they'll need to create five visualizations in Tableau. 

The first two visualizations will use the datetime datatype for the "tripduration" column to show the length of time that  bikes are checked out for all riders and genders. 

Then, they'll create heat maps that show how many trips are taken for all riders and genders by the hour for each day of the week; they’ll also display a breakdown of what days a user will check out a bike according to user type and gender.

For the third part of the assignment, **Deliverable 3: Create a Story and Report for the Final Presentation**, the learners will need to create a Story in Tableau using the five visualizations they create in Deliverable 2 and the two visualizations that they created in the module. Then, they'll provide a report in the repository README with all seven visualizations and a summary of each visualization. The report will contain three sections: analysis overview, results, and summary.

**Important:** If the learners would like to use the "Bike Utilization" graph in their Story for Deliverable 3, then we suggest creating a new column that contains the converted datatype of the "tripduration" column in Deliverable 1.

Encourage your class to begin the Challenge as soon as possible, if they haven’t already, and to use the Learning Assistants channel and the remainder of Office Hours with their instructional team for help as they progress through their work. If they feel like they need context to understand documentation or instructions throughout the week, this is where they can get it.

Open the floor to discussion and be sure to answer any questions they may have about the Challenge requirements before moving on to other areas of interest.

</details>

<details>
  <summary><strong>📣  Instructor Do: Office Hours</strong></summary>

For the remaining time, remind the students that this is their time to ask questions and get assistance from their instructional staff as they’re learning new concepts and working on the Challenge assignment.

Expect that students may ask for assistance on the following: 

* Challenge assignment 
* Further review on a particular subject
* Debugging assistance
* Help with computer issues
* Guidance with a particular tool

</details>


- - - 

## During Class 

### 1. Getting Started

| Activity Time:       0:10 |  Elapsed Time:      0:10  |
|---------------------------|---------------------------|

<details>
  <summary><strong>📣 1.1 Instructor Do: Foundation Setting (0:05)</strong></summary>

* Welcome students to class.

* Direct students to post individual questions in the Zoom chat to be addressed by you and your TAs at the end of class.

* Open the slideshow and use slides 1 - 8 to walk through the foundation setting with your class.

* **This Week - Tableau:** Talk through the key skills that students will learn this week, and let them know that they are building on their web visualization skills. 

* **Today's Objectives:** Now, outline the concepts covered in today's lesson. Remind students that they can find the relevant activity files in the “Getting Ready for Class” page in their course content. 

</details>

<details>
  <summary><strong>🎉 1.2 Everyone Do: Check-In (0:05)</strong></summary>

* Ask the class the following questions and call on students for the answers:

    * **Q:** How are you feeling about your progress so far?

    * **A:** We are building on our skill set of creating visualizations with the business intelligence tool, Tableau. It's important to look back and see what we’ve accomplished, and acknowledge that it's a lot! It’s also okay to feel overwhelmed as long as you don’t give up. The more you practice, the more comfortable you'll be coding.
    
    * **Q:** How comfortable do you feel with this topic? 

    * **A:** Let's do "fist to five" together. If you are not feeling confident, hold up a fist (0). If you feel very confident, hold up an open hand (5).

</details>



- - -

### 2. Warm-up

| Activity Time:       0:20 |  Elapsed Time:      0:30  |
|---------------------------|---------------------------|

<details>
  <summary><strong>🎉  2.1 Everyone Do: Warm-up (0:20) </strong></summary>

* You can use slides 9 - 20 to assist you with this activity.

* In this warm-up activity, students will create visualizations from data on construction permits for new residential housing units in Austin, Texas.

  * **Note:** The dataset was downloaded from [Austin's Open Data Portal](https://data.austintexas.gov/) website. The portal provides easy access to open data and information about Austin's city government. 

* Make sure the students can download and open the [instructions](Activities/01-Evr_Warmup/README.md) and the [Austin_new_residential_units.csv](Activities/01-Evr_Warmup/Resources/Austin_new_residential_units.csv) file from the AWS link. 

* Go over the instructions with the students, check for understanding, and give them a few minutes to work on their visualizations. 

* When time is up, ask for volunteers to show you their visualizations and how they were created. If there are no volunteers, open the [Austin_new_residential_units.csv](Activities/01-Evr_Warmup/Resources/Austin_new_residential_units.csv) dataset in Tableau Public and walk through creating each visualization. 

* Or, open up the [Austin_new_residential_units.twbx](Activities/01-Evr_Warmup/Solved/Austin_new_residential_units.twbx) solution and walk through creating each visualization.

* To show the total housing units for each zip code, create a new sheet and drag the `Zip Code` pill to Columns and the `Housing Units` pill to Rows. Tableau automatically aggregates on the sum of `Housing Units`. 

* Add the `Zip Code` pill to "Filters" and filter out the `NULL` and `00000` zip codes. 

  * After sorting in descending order, the chart shows that the 78704 zip code has the most new housing units, followed by the 78748 zip code. 

    ![Total housing units by zip code](Images/01-total_housing_zip.png)

* We can also visualize this data on a geospatial map. When you have data that has a geographic role, such as zip codes, Tableau automatically adds two fields to the "Measures" area of the “Data” pane: `Latitude (generated)` and `Longitude (generated)`.

  * To create a geospatial map, create a new sheet and then double-click on the `Latitude (generated)` pill and Tableau will automatically place the latitudes into Rows, since latitudes run horizontally. When you double-click on the `Longitude (generated)`, Tableau will automatically place longitudes into Columns, since longitudes run vertically. 

  * Then, drag the `Zip Code` pill to "Detail" and the `Housing Units` pill to "Color" in the “Marks” pane. This will create a heatmap based on the total number of housing units by zip code. 

  * You can edit the color on the `Housing Units` as needed. 

    ![Total housing units by zip code map](Images/01-total_housing_zip_map.png)

* To visualize the total number of housing units for each type of permit, create a new sheet and drag the `Permit Type` pill to Columns and the `Housing Units` pill to Rows, then sort in descending order. 

  ![Total housing units by Permit Type](Images/01-total_housing_permit_type1a.png)

  * We can make the x-axis labels completely visible by clicking on the right end of the x-axis and dragging to the right. 
  
    ![Total housing units by permit type with visible x-axis label](Images/01-total_housing_permit_type1b.png)

  * Or, right-click on the x-axis and select "Rotate Label." 

    ![Total housing units by permit type with visible X-axis label second option](Images/01-total_housing_permit_type1c.png)

  * This chart shows that the most permits were granted to commercial units of five or more buildings. 

* We can visualize the number of housing units by permit type for each zip code in two different ways. This chart will be similar to the first visualization. The easiest way to do this is to create a duplicate of the total housing units for each zip code, by right-clicking on the chart title and then rename the sheet. 

  ![Total housing units by permit type for each zip code](Images/01-total_housing_permit_by_zip1a.png)

  * Then, we can drag the `Permit Type` pill to "Color" and to "Filters," which will create a stacked bar chart. To add the filtering options on the right, click the drop down arrow on the `Permit Type` pill in the "Filters" pane and then select "Show Filter."

    ![Total housing units by permit type for each zip code](Images/01-total_housing_permit_by_zip1b.png)

  * The stacked bar chart shows that most of the zip codes have a lot of permits that were granted for commercial units of five or more buildings. 

  * The second option is to create multiple bar charts, one for each type of permit. 

  * Drag the `Zip Code` pill to Columns, and drag the `Permit Type` pill and `Housing Units` pill to Rows.

  * Then, filter out the `NULL` and `00000` zip codes as before. 
  
  * Add the `Permit Type` pill to "Filters," click the drop down arrow and select "Show Filter." 

    ![Permit types issued by zip](Images/01-permit_type_zip1a.png)
  
  * Next, sort in descending order on "sum of housing units within Zip Code broken down by C-105 Five or More Family Bldgs." 

    ![Total housing units by zip sorted on C-105 permits](Images/01-permit_type_zip1b.png)

  * Finally, sort in descending order on "sum of housing units within Permit Type broken down by 78705."

    ![Sum of housing units issued by permit type sorted on 78705](Images/01-permit_type_zip1c.png)

  * Using the filtering options on the right, we can show the breakdown by zip code based on the type of permit. 

* Based on the data, housing development in Austin is trending toward higher density throughout the city, with the highest density in the central corridor, or downtown. 

* If time permits, have the students create some of their own visualizations, then have them share with the class. 

* Send out the [01-Evr_Warmup/Solved/Austin_new_residential_units.twbx](Activities/01-Evr_Warmup/Solved/Austin_new_residential_units.twbx) solution for students to refer to later.

* Answer any questions before moving on to the next activity.

</details>



- - -

### 3. Maps 

| Activity Time:       0:35 |  Elapsed Time:      1:05  |
|---------------------------|---------------------------|

<details>
  <summary><strong>📣 3.1 Instructor Do: Maps (0:10)</strong></summary>

* You can use slides 21 - 28 to assist you with these activities. 

* As we have seen in the warm-up activity, creating a map in Tableau is easy. 

* Let the students know that this demonstration will take a deeper dive into creating and enhancing maps. 

* Open [Activities/02-Ins_Maps/Solved/ins_map.twbx](Activities/02-Ins_Maps/Solved/ins_map.twbx) in Tableau Public and display the map of total profits by state:

  ![Total profits by state](Images/maps1.png)

  * It is color coded by profit using the "Red-Black Diverging" palette, where profitable states are colored shades of black and states that incurred losses are colored shades of red. 

  * As pointed out in the previous activity, when there is data that has a geographic role, such as "City" and "Country" in this dataset, Tableau automatically adds two fields to the "Measures" area of the “Data” pane: `Latitude (generated)` and `Longitude (generated)`.

  * The map gives an immediate bird's-eye view of profitable and unprofitable states.

* To generate this map, simply drag the `Profit` pill to "Color" in the "Marks" pane:

  ![Profit pill added to color marks pane](Images/maps2.png)

  * The colors can be tweaked by clicking on the dropdown menu in the legend and choosing "Edit Colors":

  ![Adjusting colors in Tableau](Images/maps3.png)

* To simply categorize profitable states against unprofitable states, we can create a custom logical function (`Analysis` -> `Create Calculated Field`):

  ![Calculated field for profits](Images/maps4.png)

  ![profitable and unprofitable states](Images/maps6.png)

  * The pill for the custom field is dragged to the "Color" marks to view this map.

* Also, show the class that Tableau has built-in layers to add data from the U.S. Census!

  * Click on "Map" in the menu, then click "Map Layers."

  ![Map layers in Tableau](Images/maps6.png)

  * We are presented with options for borders.

  ![Map layer options](Images/maps7.png)

* Send out the [02-Ins_Maps/Solved/ins_map.twbx](Activities/02-Ins_Maps/Solved/ins_map.twbx) Tableau Public workbook for students to refer to later.

* Ask the class the following questions and call on students for the answers:

    * **Q:** Where have we used this before?

    * **A:** We created a symbol marker map, which is similar to the state map, in Lesson 14.2.7.

    * **Q:** How does this activity equip us for the Challenge?

    * **A:** We will not need to create a map in the Challenge, but it's good to know how to create a map in Tableau. 

    * **Q:** What can we do if we don't completely understand this?

    * **A:** We can refer to the lesson plan and reach out to the instructional team for help.

* Take a moment to address any questions before moving on to the student activity.

</details>

<details>
  <summary><strong>🎉 3.2 Everyone Do: Maps (0:25)</strong></summary>

* In this activity, students will chart the intensity of earthquakes over time and create a map comparing the magnitude of earthquakes versus median household income.

* Make sure the students can download and open the [instructions](Activities/03-Evr_Maps/README.md), the [student_earthquakes_database.csv](Activities/03-Evr_Maps/Resources/student_earthquakes_database.csv), and the [employment.csv](Activities/03-Evr_Maps/Resources/employment.csv) files from the AWS link. 

* Go over the instructions with the students, check for understanding, and give the students a few minutes to work on their visualizations. 

* When time is up, ask for volunteers to show you their visualizations and how they were created. If there are no volunteers, open the [earthquakes_database.csv](Activities/03-Evr_Maps/Resources/earthquakes_database.csv) dataset into Tableau Public and walk through creating each visualization. 

*  **Earthquake Maps**

* First, we'll determine if there is a relationship between the 2017 median household income and the magnitude of earthquakes from 2010 to 2016.

  * Add the `Longitude` and `Latitude` pills to Columns and Rows, respectively, and then change the category of both pills to `Dimension`.

   ![Adding latitude and longitude](Images/maps8.png)

  * Next, add the `Magnitude` pill to the "Color" and then adjust the magnitude from 5.5 to 10.0. 

    ![Adjust the magnitude](Images/maps9.png)
  
  * Add the `Magnitude` pill to the "Color" in the "Marks" pane, then change the color to "Red-Gold" and select the "Stepped Color" box with 5 "Steps." This will make the stronger earthquakes larger and colored red. 

    ![Adjusting color for earthquakes](Images/maps10.png)

  * Next, add the `Magnitude` pill to "Size" in the "Marks" pane and change the data to an "Attribute," then add the `Date` and `Source` pills to the "Tooltip" in the "Marks" pane.

  * Add the `Date` pill to the "Filters" pane, select "Years," then click the boxes for the years 2010 to 2016.

    ![Major earthquakes from 2010 - 2016](Images/maps11.png)

  * To add the census data, in the "Map Layers" we select "Household Income (median)” from the "Data Layer." Then, select "County" and change the color to "Area Green." 

    ![US census data and earthquakes](Images/maps12.png)

* To determine whether there has been any trend in the magnitude of earthquakes measured globally over the years, add the `Magnitude` pill to Rows and change the measure to "Average," then add the `Date` pill to Columns and change the time to "Quarter" for all years. 

  ![Average magnitude of global earthquakes from 1965 - 2016](Images/maps13.png)

  * The chart shows that there is no relationship between the average magnitude of earthquakes and the year. However, sometimes a trend can become clearer by adjusting the range of the axis.

  * It is possible to adjust the range of the y-axis by right-clicking on it, then choosing "Edit Axis" and changing the range from 5.5 to the maximum value in the dataset, 6.491013053. 

    ![Edit the y-axis to change the scale](Images/maps14.png)

  * After adjusting the y-axis, we can see that the average magnitude of earthquakes was higher between 1965 and 1970. 

    ![Average magnitude of global earthquakes from 1965 - 2016 adjusted](Images/maps15.png)

* To create a global map of earthquakes, we will need to adjust the Richter scale, which is logarithmic, so that it uses exponential values to size earthquakes on the map.

    ![Adjusting the magnitude to exponential values](Images/maps16.png)

    * The CSV file is opened in Excel, and a new column called `Magnitude ^ 10` is created.
    * For example, the formula in cell `J2` is defined as `=I2^10` and applied to the entire column.
    * This pill is added to "Size" in the "Marks” pane.
  
  * Then, the `Magnitude` pill is added to the "Color" in the "Marks" pane, and the magnitude range is adjusted from 5.5 to 10.0. 

  * There are several options to color the earthquakes:

    * Colors can be binned into `Steps`.
    * `Orange-Blue Diverging` originally had orange to the left and blue to the right, but this has been reversed.
    * The upper end of earthquake magnitude is defined as 9.1.
    * The center of the color range is defined as a magnitude of 7.

    ![Adjusting the colors of the earthquakes](Images/maps17.png)

  * After adjusting the colors, the map should look similar to this:

    ![Global earthquakes](Images/maps18.png)

* **Unemployment Maps**

* To create maps for unemployment between 2008 and 2016 and 1990 and 1998, the `Latitude (generated)` and `Longitude (generated)` pills are added to Rows and Columns, respectively.

* The following is applied to the chart:

  * Add the `Year` pill to the "Filters" pane, and filter the data between 2008 and 2016 and 1990 and 1998, respectively, for each chart.   

  * The `Rate` (or `Unemployment`) pill is added to the "Color" in the "Marks" pane, and the measure is changed to "Average." 

  * The `State` and `County` pills are added to the "Detail" pill in the "Marks" pane. 

    ![Unemployment between 2008 and 2016](Images/maps19.png)

    ![Unemployment between 1990 and 1998](Images/maps20.png)
  
* To create a map of counties with the highest rates of unemployment between 2008 and 2016, add the `Latitude (generated)` and `Longitude (generated)` pills to Rows and Columns, respectively; then, apply the following to the chart:

  * The "Household Income (median)” from the "Data Layer" by "State" is added to the map. 

  * The `Year` pill is added to the "Filters" pane, and the data is filtered between 2008 and 2016. 

  * The `Rate` (or `Unemployment`) pill is added to the "Color" in the "Marks" pane, and the measure is changed to "Average." 

  * The `State` and `County` pills are added to the "Detail" pill in the "Marks" pane. 

  * The `Rate` (or `Unemployment`) pill is added to the "Filters" pane, and the data is changed to "Dimension" and filtered between 18.0 and 25.0.

    ![Highest rates of unemployment between 2008 and 2016](Images/maps21.png)

* Using other census map layers, the students can create similar maps that depict the relationship between race and unemployment on a county-by-county basis.

* Send out the [earthquakes.twbx](Activities/03-Evr_Maps/Solved/earthquakes.twbx) and [unemployment.twbx](Activities/03-Evr_Maps/Solved/unemployment.twbx) files for students to refer to later. 

* Answer any questions before moving on to the next activity.

</details>



- - -

### 4. Airline Safety Dashboard

| Activity Time:       0:25 |  Elapsed Time:      1:30  |
|---------------------------|---------------------------|

<details>
  <summary><strong>📣 4.1 Instructor Do: Dashboard (0:05)</strong></summary>

* You can use slides 29 - 31 to assist you with these activities. 

* Explain that dashboards allow a bird's-eye view of several visualizations. In Tableau, we can also have elements that interact with each other.

* Open up the [dashboard.twbx](Activities/04-Ins_Dashboard/Solved/dashboard.twbx) workbook and show each worksheet, then show the worksheet named "Profit Dashboard." 

  ![Profit map and profit by category added to a dashboard](Images/dashboard1.png)

  * We can have multiple visualizations on a single page.

* To create a new dashboard, click the "New Dashboard" button at the bottom of the screen.

  ![Add a new dashboard tab](Images/dashboard2.png)

  * Then, drag each sheet to be visualized into the parent area, which is called the "container."

* To create interactive "actions" that affect more than one visualization, take the following steps:

  * Go to "Dashboard," then "Actions."

  ![dashboard "Actions" options](Images/dashboard3.png)

  * Click "Add Action" and, in this case, "Filter."

  ![Using the filter on actions](Images/dashboard4.png)

  * Click on "Select" under "Run action on:". Then, specify the source and target sheets for the action.

  ![Edit dashboard filter](Images/dashboard5.png)

* In order to move each chart, click on the dropdown arrow, then click "Floating."

  ![Select "Floating" for the chart on the dashboard](Images/dashboard6.png)

* And now the charts are interactive. For example, clicking on Texas in the map changes the "Profits by Category" bar chart, which will now reflect only the values for Texas across the years in the three product categories.

  ![Interactive charts on the dashboard](Images/dashboard7.png)

* Send out the [04-Ins_Dashboard/Solved/dashboard.twbx](Activities/04-Ins_Dashboard/Solved/dashboard.twbx) workbook for students to refer to later.

* Ask the class the following questions and call on students for the answers:

    * **Q:** Where have we used this before?

    * **A:** Creating a dashboard was covered in Lesson 14.4.1.

    * **Q:** How does this activity equip us for the Challenge?

    * **A:** The students may need to create a dashboard as part of the story they are required to create to complete the Challenge. 

    * **Q:** What can we do if we don't completely understand this?

    * **A:** We can refer to the lesson plan and reach out to the instructional team for help.

* Take a moment to address any questions before moving on to the student activity.


</details>

<details>
  <summary><strong>🎉 4.2 Everyone Do: Airline Safety Dashboard (0:20)</strong></summary>

* In this activity, students will explore the safety of the world's airlines. The dataset used here is from [fivethirtyeight.com](https://github.com/fivethirtyeight/data/tree/master/airline-safety).

* Make sure the students can download and open the [instructions](Activities/05-Evr_Airline_Dashboard/README.md) and the [airline-safety.csv](Activities/05-Evr_Airline_Dashboard/Resources/airline-safety.csv) files from the AWS link. 

* Go over the instructions with the students and let them know that this activity will be an open-ended exploration of the data. 

* Let students work on creating some visualizations for 8 minutes. 

* If students are having difficulty, share some of the visualizations in the [airline.twbx](Activities/05-Evr_Airline_Dashboard/Solved/airline.twbx) workbook.  

* Once time is up, have the students spend some time adding visualizations to a dashboard. 

* Open the [airline.twbx](Activities/05-Evr_Airline_Dashboard/Solved/airline.twbx) workbook and briefly go over how to add visualizations to a dashboard. 

* If time permits, ask some of the students to share their dashboards with the class. 

* Send out the [05-Evr_Airline_Dashboard/Solved/airline.twbx](Activities/05-Evr_Airline_Dashboard/Solved/airline.twbx) workbook for students to refer to later.

* Answer any questions before moving on to the next activity.

  </details>

  <sub>[Having issues with this activity? Report a bug!](https://bit.ly/3sEIcwa)</sub>


- - -

### 5.Creating Stories and Presentations

| Activity Time:       0:25 |  Elapsed Time:      1:55  |
|---------------------------|---------------------------|

<details>
  <summary><strong>📣 5.1 Instructor Do: Storytelling (0:05)</strong></summary>

* You can use slides 32 - 34 to assist you with this activity. 

* Sometimes a single chart is not sufficient to provide viewers with all of the information they need. In fact, visualizations are sometimes only helpful when placed alongside other charts/data.

  * Tableau uses stories to simplify the process of bringing multiple charts together in one place.

* Open up the [story_board.twbx](Activities/06-Ins_Storytelling/Solved/story_board.twbx) workbook within Tableau and navigate into the "Shipping Overview" tab, pointing out all the text boxes at the top of this view.

  ![Story Overview Boxes](Images/02-Storytelling_StoryBoxes.png)

  * Click through a couple of the text boxes at the top of the view, discussing with the class how each text box is associated with a visualization from the workbook.

* Create a new story within the workbook by selecting the "New Story" button from the bottom tabs of the application.

  ![Selecting the new story button on bottom tab](Images/02-Storytelling_NewStoryPoint1.png)


  * The view on the left side of the page will now contain all of the sheets in the current workbook, and they can be added to the story by dragging them into the main area.

  * Captions for the story points can be added/edited by clicking on the gray box at the top of the main view.

* To add a new page to a story, navigate to the "New Story Point" and select either "Blank" to create a blank page or "Duplicate" to create a page based on a preexisting page.

  ![Add a new story](Images/02-Storytelling_NewStoryPoint2.png)

* Text boxes may also be added to the page by dragging the "Drag to Add Text" element onto the page. This will allow for more detailed explanations.

  ![Add text boxes to the story step 1](Images/02-Storytelling_textbox.png)

  ![Adding a text box to a chart on the story page](Images/02-Storytelling_StoryPage.png)

* Send out the [06-Ins_Storytelling/Solved/story_board.twbx](Activities/06-Ins_Storytelling/Solved/story_board.twbx) workbook for students to refer to later.

* Ask the class the following questions and call on students for the answers:

    * **Q:** Where have we used this before?

    * **A:** Creating a story was covered in Lesson 14.5.1.

    * **Q:** How does this activity equip us for the Challenge?

    * **A:** Students will need to create a story from the visualizations to complete the Challenge.

    * **Q:** What can we do if we don't completely understand this?

    * **A:** We can refer to the lesson plan and reach out to the instructional team for help.

* Take a moment to address any questions the class may have about stories before moving on to the student activity. 

  </details>


<details>
  <summary><strong>🎉 5.2 Everyone Do: Creating Stories and Presentations (0:20)</strong></summary>

* In this activity, students will create a story using the visualizations they made in one of the "Student Do" or "Everyone Do" activities from either class.

* Give the students 10 to 12 minutes to create a story, then ask for volunteers to present their story. 

* Ensure that each story and text box added to the chart clearly describes or summarizes the visualization. 

  </details>

 <sub>[Having issues with this activity? Report a bug!](https://bit.ly/3kIC6rH)</sub>


- - - 

### 6. Ending Class 

| Activity Time:       0:05 |  Elapsed Time:      2:00  |
|---------------------------|---------------------------|

<details>
  <summary><strong>📣  6.1 Instructor Do: Review </strong></summary>

* Before ending class, review the skills that were covered today and mention where in the module these skills are used: 
  * Creating geospatial maps was covered in **Lesson 14.3.1**.
  * Creating a dashboard was covered in **Lesson 14.4.1**.
  * Creating a story was covered in **Lesson 14.5.1**. 

* Answer any questions the students may have.

</details>



- - - 

© 2021 Trilogy Education Services, LLC, a 2U, Inc. brand.  Confidential and Proprietary.  All Rights Reserved.
