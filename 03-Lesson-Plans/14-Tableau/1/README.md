# Module 14 Class 1: Creating Visualizations with Tableau

## Overview

This week, we will be learning how to visualize data stories with Tableau. In this unit, students will learn how to import data into Tableau, create basic visualizations, change data types of columns, join data sources, customize visualizations, create calculated fields, and create dashboards and stories. 

In today's class, students will import Excel spreadsheets and CSV files into Tableau, then create basic visualizations, change data types of columns, join data sources, customize visualizations, and create calculated fields.  

## Learning Objectives

By the end of class, students will be able to:
 
* Import data from various sources into Tableau.
* Create basic visualizations in Tableau.
* Customize their visualizations.
* Create custom calculations.


- - -

## Instructor Notes

* The activities in this class will complement Lessons **14.0.1: Tableau Basics** through **14.3.3: Find the Number of Rides by Gender**.  The students will benefit from these activities if they‘ve progressed through these lessons, which cover the following concepts, techniques, and tasks:  

  * Download and install Tableau Public 
  * Set up their Tableau environment
  * Import data into Tableau and connect to a data source
  * Change data types of columns and join data sources
  * Understand how to use the data and analytics panes, and the “Marks” section
  * Understand the difference between discrete and continuous measures
  * Create pie, bar, and symbol marker charts
  * Create a calculated field for gender

* If you have issues with any of today's activities, you may report it [here](http://tiny.cc/BootCampFeedback).

## Instructor Prep

* Welcome to Tableau week! Coding takes a back seat this week as the students focus on creating visualizations. While Excel and VBA allow you to be very flexible in how you manipulate your data, Tableau allows you to more easily discover visualizations you can apply to your data, even ones that aren’t readily available in Excel, like world maps.

* Tableau allows more flexibility when changing data sources or the type of charts you want to use. You can also add data and change scenarios on the fly without much overhead. The drag-and-drop abilities of Tableau make it incredibly simple to integrate more data (and it can handle **a lot** of data, more so than Excel).

* Different tools for different uses make it easier  to adapt and adjust to give your stakeholders what they need.

* The students will be using the public version of Tableau. Although there is a 2-week free trial for Tableau Desktop, a lot of platforms do not extend student discounts or trials to students in continuing-education programs or those without university email addresses.

* Tableau Public is a free version of the software that provides all the same tools as Pro (Desktop). However, because it’s free, it requires all data that is input to be freely accessible, and it has a limit of 1 million rows. This version should not be used if you’re dealing with sensitive or privileged datasets. This version also does not allow saving to your machine, and you must save to their server.

## Slides

[Tableau Day 1 slideshow](https://docs.google.com/presentation/d/1KvuQTRFhzt_ie6W1h5BiVoOKwZhzK5VVdCVVKFG-3yg/edit?usp=sharing)

## Student Resources

If students were unable to download today's [activity resources](https://2u-data-curriculum-team.s3.amazonaws.com/data-viz-online-lesson-plans/14-Lessons/14_1-Student_Resources.zip) from Canvas, please share them with the students.

- - - 

## Before Class

### 0. Office Hours

| Activity Time: 0:30       |  Elapsed Time:     -0:30  |
|---------------------------|---------------------------|

<details>
  <summary><strong> 📣 0.1 Instructor Do: Office Hours</strong></summary>

* Before you begin class, hold office hours. Office hours should be driven by students. Encourage students to take full advantage of office hours by reminding them that this is their time to ask questions and get assistance from instructional staff as they learn new concepts.

* Expect that students may ask for assistance. For example: 

  * Further review on a particular subject
  * Debugging assistance
  * Help with computer issues
  * Guidance with a particular tool

</details>

- - - 

## During Class 

### 1. Getting Started

| Activity Time:       0:20 |  Elapsed Time:      0:20  |
|---------------------------|---------------------------|

<details>
  <summary><strong>📣 1.1 Instructor Do: Foundation Setting (0:10)</strong></summary>

* Welcome students to class.

* Direct students to post individual questions in the Zoom chat to be addressed by you or your TAs at the end of class.

* Open the slideshow and use slides 1 - 12 to walk through the foundation setting with your class. 

* **Big Picture:** This is an opportunity to zoom out and see the big picture of where they are in the program. Take a moment to mention some real-world examples that show the value of what they’re learning this week.

* **Program Pointers:** Talk through some of the key logistical things that will help students stay on track. This is an opportunity to speak to what students may need when they're at this particular point of the program. 

* **This Week - Tableau:** Talk through the key skills students will be learning this week. Let the students know that the Day 1 activities will focus on getting students to create basic visualizations, change data types of columns, join data sources, customize visualizations, and create calculated fields. On Day 2, the students will apply what they learned on Day 1 to create dashboards and stories in Tableau. 

* **This Week's Challenge:** For this week's Challenge, let the students know that they'll be using the NYC Citi Bike. First, they’ll use Pandas to change the datatype of the "tripduration" column from integer to datetime. Then, using the converted datatype, they’ll create a set of visualizations to show the length of time that bikes are checked out for all riders and genders, the number of bike trips for all riders and genders for each hour of each day of the week, and the number of bike trips for each type of user and gender for each day of the week. After adding these new visualizations to the ones they created in this module, they’ll create a story in Tableau. 

* **Career Connection:** Let students know how they will use the skills covered this week throughout their careers. It's important for them to know the "why." Give examples of when they may be used in work or when you have used those skills in your workplace. 

* **How to Succeed This Week:** Remind your students that they may have moments of frustration this week as they learn something complex. These moments are great for deepening their knowledge. Use the side material to outline some of the topics that they may find tricky in this module. Consider sharing something about your personal learning journey. It helps students to recognize that everyone starts somewhere and they are not alone.

* **Today's Objectives:** Now, outline the concepts that will be covered in today's lesson. Remind students that they can find the relevant activity files in the “Getting Ready for Class” page in their course content.  

</details>

<details>
  <summary><strong>🎉  1.2 Everyone Do: Check-In (0:05)</strong></summary>

* Ask the class the following questions and call on students for answers:

    * **Q:** How are you feeling about your progress so far?

    * **A:** We are starting to build your skillset. It’s also okay to feel overwhelmed as long as you don’t give up.

    * **Q:** How comfortable do you feel with this topic? 

    * **A:** Let's do "fist to five" together. If you are not feeling confident, hold up a fist (0). If you feel very confident, hold up an open hand (5).

</details>

<details>
  <summary><strong> 📣 1.3 Instructor Do: Introduction to Tableau (0:05) </strong></summary>

* You can use slides 13 - 22 to assist you with this section.

* Make sure everyone has installed [Tableau Public](https://public.tableau.com). The instructions for downloading and installing Tableau Public are covered in **Lesson 14.1.1: Install Tableau Public**. 

* Remind the students that Tableau Public is a completely free version of the Tableau software that includes the majority of features included within Tableau Desktop. The main differences between the two versions are working with multiple types of data sources, like SQL databases, and working with data files that are not shared with the public. 

* Inform the students that although they can download and explore the 14-day trial version of the paid software, we recommend that they do not unless they are going to buy a paid subscription, and that all assignments in this unit can be completed with the free version.

* Tableau is an extremely powerful business intelligence application that allows its users to create in-depth visualizations in very little time.

    ![Tableau Logo](Images/01-IntroTableau_Logo.png)

  * Like Microsoft Excel, Tableau focuses extensively on allowing its users to manipulate tables of data and create visualizations without any need for additional programming.

  * Tableau also utilizes a drag-and-drop-style interface so that its users can easily create tables and charts, and perform analysis without much difficulty.

* Take a moment to point out some of the [Tableau Public feature projects](https://public.tableau.com/en-us/gallery/?tab=featured&type=featured) that users have created.

  ![Tableau Public Gallery](Images/01-Installation_Gallery.png)

  * One Tableau feature is the ability to share projects and visualizations with your community.

  * Not only can visualizations be shared on the Tableau site, they can also be embedded on webpages.

  * Point out how varied and interesting the projects within the gallery are. These are all things that users can create with Tableau upon mastering the software.

* Explain to the class that Tableau is essentially the "easy mode" of data visualization, and that the class will be able to create many of their visualizations from the past in very little time using this application.

</details>



- - -


### 2. Loading & Exploring Data

| Activity Time:       0:30 |  Elapsed Time:      0:50  |
|---------------------------|---------------------------|

<details>
  <summary><strong> 📣 2.1 Instructor Do: Loading and Exploring Data (0:05)</summary></strong>

* You can use slides 23 - 24  to assist you with this section.

* Have everyone open Tableau Public, then briefly explain that many different data sources can be connected to it.

  * With Tableau Public, you are able to connect to an Excel file, a text file (`.txt`, `.csv`, `.tab`, `.tsv` files), JSON, PDF, and others. 
 
    ![Tableau Public Data Sources](Images/02-LoadingData_DataSources_Public.png)

  * With Tableau Desktop, you have the same options as Tableau Public, but you can also connect to a multitude of servers, like MySQL, Oracle, Amazon Redshift, Google Sheets, and more.

    ![Tableau Desktop Data Sources](Images/02-LoadingData_DataSources_Desktop.png)

  * What makes this noteworthy is that Tableau allows users to mix and match data from vastly different sources without needing to translate them into something like a Pandas DataFrame. The loading, exploration, and manipulation of data is all built-in.

* Next, have everyone select "Microsoft Excel" from the list of data sources available, and load [GlobalSuperstoreOrders2016.xlsx](Activities/01-Ins_LoadingData/Resources/GlobalSuperstoreOrders2016.xlsx) within Tableau.

  * After the data has been imported into Tableau, explain how individual sheets from the original Excel workbook need to be dragged from the navigator into the main application.

  * Do this with the `Orders` sheet, then point out how, once the data has been loaded, a preview is provided in the main area of the application.

    ![Drag orders to load](Images/02-load02.gif)
  
  * Their connection should look like the following:

    ![Orders table](Images/02-LoadingData_Table.png)

* It is important to point out that Tableau does not allow users to change values contained in the cells of a dataset, but it is possible to create new columns based on the values of other columns.

  * Any changes made to the dataset within Tableau will not affect the original dataset. The purpose of Tableau is to create visualizations: manipulating data is not its strong suit.

* Filtering data is very simple, though, as all Tableau users need to do is click on the "Add" button beneath the `Filters` text in the top-right corner of the application, click "Add..", and then select a column to filter by.

  ![Filtering a  Column](Images/02-LoadingData_FilterColumn.png)

  * After selecting which column to filter by, the values to filter are chosen either manually or based on some kind of condition.

    ![Filtering Values](Images/02-LoadingData_FilterValues.png)

  * Depending on the datatype stored in a column, different filters may or may not be available. Selecting the "Order Data" column, which has a date datatype, allows users to filter rows based on date ranges.

    * First click the the `Filters` text in the top-right corner, then select the "Order Date" column to filter by, and double click on the "Range of Dates".

      ![Select the Range of dates to filter by](Images/02-LoadingData_FilterDate1.png)

      ![Filtering Dates](Images/02-LoadingData_FilterDate2.png)

* Ask the class the following questions and call on students for the answers:

    * **Q:** Where have we used this before?

    * **A:** Importing data into Tableau was covered in Lesson 14.1.4.

    * **Q:** How does this activity equip us for the Challenge?

    * **A:** We will need to import data into Tableau to complete the Challenge.

    * **Q:** What can we do if we don't completely understand this?

    * **A:** We can refer to the lesson plan and reach out to the instructional team for help.

* Answer any questions before proceeding to the next activity.

</details>

<details>
  <summary><strong> 📣 2.2 Instructor Do: Building Basic Visuals (0:10) </strong></summary>

* You can use slide 25 to assist you with this section.

* Create a new Tableau project and connect it to the [GlobalSuperstoreOrders2016.xlsx](Activities/02-Ins_BasicVisuals/Resources/GlobalSuperstoreOrders2016.xlsx) file provided. Then, drag the `Orders` sheet into the main area.

* This demonstration will cover how to create basic visualizations. 

* With [GlobalSuperstoreOrders2016.xlsx](Activities/02-Ins_BasicVisuals/Resources/GlobalSuperstoreOrders2016.xlsx) loaded, show how users can edit individual worksheets at the bottom of the application.

  ![Worksheets Panel](Images/03-BasicVisuals_Worksheets.png)

* Creating visualizations in Tableau is nearly identical to creating pivot tables in Excel. Users click and drag the headers of their original dataset into specific fields (Columns, Rows, Filters, or Marks) in order to create a chart.

  ![Tableau Chart Screen](Images/03-BasicVisuals_ChartArea.png)

* Quickly explain the difference between `Dimensions` and `Measures`:  

  * `Dimensions` are located in the upper part of the Data Pane section. They are the qualitative values in your dataset, such as
names, dates, and geographical data. You can use dimensions to categorize, segment, and reveal the details in your data.

  * `Measures` are located in the lower part of the Data Pane section. They are the quantitative
values in your dataset, which are usually numerically measured. You can apply calculations to measures and they can be aggregated. When you drag a measure into Columns, Rows, Filters, or Marks, Tableau automatically applies an aggregation to that measure.

  ![Dimensions and Measures on the left side under the Data Pane](Images/03-Dimensions_Measures.png)

* Drag the `Category` pill from the `Dimensions` panel into `Rows` to show the class how a small table containing the three categories is created.

* By dragging `Segment` into `Rows` and placing it after the `Category` pill, the table is made slightly more complex. Now, each category within the visualization has been split into three distinct parts.

  ![Category by Segment](Images/03-Basic_Category_Segments.png)

* Dragging "Quantity" from the `Measurements` panel into `Columns` creates a bar chart showing the quantity of orders per segment per category.

  ![The quantity of orders per segment per category.](Images/03-Basic_bar_chart.png)

  * Tableau has automatically aggregated `Quantity` into a sum. This will be discussed in greater detail later.

* The chart can then be made more detailed by adding more elements. By adding `Market` into `Columns`, for example, multiple charts are created to show the quantity of orders per segment per category within each geographic market.

  ![The quantity of orders per segment per category within each geographic market](Images/03-Basic_bar_chart_add_elemets.png)

* Creating visualizations within Tableau is easy. Click and drag the elements that should be visualized into their respective fields, and Tableau will automatically create a visual based on them.

  * If users would like to change what kind of visualization to employ, they can click the `Show Me` button at the top right of the application and select the desired charting style.

    ![Use the Show Me feature](Images/03-BasicVisuals_ShowMe.png)

* Next, show the students how to create multiple line graphs from aggregated data.  

* First, create a new worksheet within Tableau. Drag `Sales` into the `Rows` section.

  ![The sum of sales](Images/03-Sum_sales.png)

  * Point out that a bar chart was created that visualizes the total sales made by the company in question. This is because the `Sales` pill is being measured by default by its sum.

* The type of calculation performed on a `Measures` pill can be changed by clicking on the pill, selecting "Measure" from the drop-down menu, then picking one of the available calculation types.

  ![Change Measures](Images/03-BasicVisuals_Measures.png)

* Next, drag `Order Date` into the `Columns` field to create a very basic line chart.

  ![The year for sum of sales](Images/03-Year_Sum_sales.png)

* Point out to the class how Tableau has aggregated the dates at the year level. To expand this to include quarters, simply click on the plus symbol within the `YEAR` pill.

    ![Line Graph](Images/03-BasicVisuals_LineGraph.png)

  * Explain that Tableau, by default, visualizes at the **least** granular level. In this case, it displays the yearly results by default.

* In order to compare how Q1 has performed over the years, simply move the `QUARTER` pill before `YEAR`.

    ![Line Graph Pivot](Images/03-BasicVisuals_LineGraphPivot.png)

* Explain to the class how the best way to learn Tableau is to dive into the application and test it out manually.

* Send out the [02-Ins_BasicVisuals/Solved/Complete.twbx](Activities/02-Ins_BasicVisuals/Solved/Complete.twbx) Tableau Public workbook for students to refer to later.

* Ask the class the following questions and call on students for the answers:

    * **Q:** Where have we used this before?

    * **A:** Learning how to use Tableau and creating basic visuals were covered in Lessons 14.2.5 - 14.2.7.

    * **Q:** How does this activity equip us for the Challenge?

    * **A:** We will need to know how to create basic visualizations in order to create the more complex visualizations required to complete the Challenge.

    * **Q:** What can we do if we don't completely understand this?

    * **A:** We can refer to the lesson plan and reach out to the instructional team for help.

* Take a moment to address any questions before moving on to the student activity.

</details>

<details>
  <summary><strong>🎉  2.3 Everyone Do: Explore Data (0:15)</strong></summary>

* You can use slide 26 to assist you with this section.

* In this activity, students will be given visualizations, which they will attempt to recreate using Tableau.

* Make sure the students can download and open the [instructions](Activities/03-Evr_Exploration/README.md) from the AWS link.

* Go over the instructions with the students and check for understanding.

* Have everyone open a new Tableau Public workbook, import the `GlobalSuperstoreOrders2016.xlsx` dataset, and drag the 'Orders' table to connect to the table. 

* Ask for volunteers to help create each visualization. If there are no volunteers, walk through how to create each visualization with the steps below, or open the solved [sales.twbx](Activities/03-Evr_Exploration/Solved/sales.twbx) in Tableau Public.

* For the first visualization – the customers with the highest sales amount:

  1. In a new sheet, drag the `Customer Name` pill to Rows. A pop message may appear to ask you how you want to handle the data. Select "Filter and then add." 

      ![Customer Name by Sum of Sales](Images/04-explore1a.png)
  
  2. Then add the `Sales` pill to Columns.

      ![Customer Name by Sum of Sales](Images/04-explore1b.png)

  3. Then, to change the color of the bars, click on the "Color" in the "Marks" section and select a desired color. 
  
      ![Changing bar color](Images/04-explore2a.png)

  4. To sort the data, click on the sort button:

      ![Sorting the data ](Images/04-explore2b.png)

* To create the second visualization, the most profitable customers, create a new sheet and repeat step 1 above, but this time add `Profit` to Columns instead of `Sales`. 

  ![Sum of Profit vs. Sales](Images/04-explore3a.png)

  1. To adjust the axis at the bottom, right-click at the bottom along the axis and select "Edit Axis."

      ![Editing the X-axis](Images/04-explore3b.png)

  2. Then, under "Range," click the "Fixed" button, and add a "0" into the "Fixed Start" field. This will filter out negative profit figures. 

      ![Setting the range on the X-axis](Images/04-explore3c.png)

  3. After sorting and changing the color, the chart should now look like this:

    ![Final chart of most profitable customers](Images/04-explore3d.png)

* Next, to chart the states with the highest average profit create a new sheet and do the following:

  1. Add `Profit` to the Columns, then select `Average` under `Measure`.

    ![Average Profit](Images/04-explore4a.png)

  2. Next, add "Country" to the "Filters" pane, scroll down and select "United States."  

    ![Fitlering on Country for the United States](Images/04-explore4b.png)

  3. Then, add "State" to the Rows and click "Filter and then add" to add all the states for the United States filtering.

    ![Filtering on States](Images/04-explore4c.png)

  4. Then, select all the states. 

    ![Selecting all the states](Images/04-explore4d.png)

  5. After sorting by descending average profit, the chart should look like this:

    ![Final most profitable states](Images/04-explore4e.png)


* To display a monthly timeline, create a new sheet and drag the `Sales` pill to Rows, then obtain its sum. Then, drag `Order Date` to Columns.

  ![Year of order vs. sum of sales](Images/04-explore5a.png)

  * This, however, is not what we want. There are two ways to drill down to the monthly level: 
      * One is to click on the `+` symbol on the `YEAR (Order Date)` pill, then get rid of undesired levels. 
      * The other is to click on the arrow in the pill and select `Month`:

    ![Select the Months to display on the chart](Images/04-explore5b.png)

    ![Month of order vs. sum of sales](Images/04-explore5c.png)

* Finally, to visualize profit by region and product category, create a new sheet and drag the `Category` and `Region` pills to Columns, and create a sum of the `Profit` pill in Rows.

  ![Category and Region vs sum of profit](Images/04-explore6a.png)

  * Next, add the `Country` to the "Filters" section and select "United States."

    ![Fitler countries for the United States only](Images/04-explore6b.png)

  * Then add the `Region` pill to the "Color" Marks, the chart should now look like this:

    ![Final profit by region and product category](Images/04-explore6c.png)
  
* Send out the [03-Evr_Exploration/Solved/sales.twbx](Activities/03-Evr_Exploration/Solved/sales.twbx) file for students to refer to later.

* Answer any question before moving on to the next activity. 


</details>




---

### 3. No-Show Tableau Visualization

| Activity Time:       0:20 |  Elapsed Time:      1:10  |
|---------------------------|---------------------------|

<details>
  <summary><strong> ✏️ 3.1 Students Do: No-Show Tableau Visualization (0:15)</strong></summary>

* You can use slides 27 - 29 to assist you with this section.

* Students will now spend some time creating a series of visualizations about what kinds of people are more/less likely to show up to doctor appointments.

    ![No Show Ages](Images/05-NoShows_AgeAppointments.png)

* Make sure the students can download and open the [instructions](Activities/04-Stu_NoShow_Visualization/README.md) and the [no_shows.csv](Activities/04-Stu_NoShow_Visualization/Resources/no_shows.csv) file from the AWS link. 

* Go over the instructions in the README, and then divide students into breakout groups of 3-5. They should work on the solution by themselves but can reach out to others in their group for tips.

* Let students know that they may be asked to share and walk through their work at the end of the activity.

</details>

<details>
  <summary><strong> ⭐ 3.2 Review: No Shows (0:05)</strong></summary>

* Once time is complete, ask for volunteers to share their solution. Remind them that it is perfectly alright if they didn't complete the activity. 

* To encourage participation, you can ask the students to help you create each chart. 

* If there are no volunteers, open up the solved [no_shows.twbx](Activities/04-Stu_NoShow_Visualization/Solved/no_shows.twbx) within Tableau and walk through the application with the class, answering whatever questions students may have.

* The first step for this activity is to drag `Age` to Columns and `no_show.csv (Count)` to Rows. 

  ![No shows by age - measure](Images/05-noshow1a.png)

* The `Age` must also be converted from measure to dimension by clicking on the arrow on the pill.

  ![No shows by age - dimension ](Images/05-noshow1b.png)

* To split up the no-show results by gender, drag `Gender` into Rows:

  ![No shows by age and gender](Images/05-noshow2a.png)

  * Male patients, overall, seem to have fewer appointments across age groups!

* Next, to stratify the results by no-show appointments, drag `No-show` to columns:

  ![No shows by age, gender, and if they were a no-show or not](Images/05-noshow2b.png)

* In the next visualization, students were asked to compare no-shows by neighborhood. This can be done in the following way:

  ![No-shows by neighbourhood](Images/05-noshow3a.png)

  * `No-show` and `no_show.csv (Count)` are dragged to Columns, and `Neighbourhood` to Rows.

* It can also be visualized as follows:

  ![No-shows by neighbourhood](Images/05-noshow3b.png)

  * `No-show` is moved to Rows instead of Columns.

* In the next visualization, students were asked to visualize the number of no-show patients by the day of the week:

  ![No-shows by weekday stacked bar chart](Images/05-noshow4a.png)

* Since we're counting the number of no-show appointments, it makes sense to drag `No-show` to Rows, and to visualize this measure vertically. And since we're tallying the number of no-shows by day of the week, it makes sense to drag `Scheduled Day` into Columns:

  ![No-shows by year line chart](Images/05-noshow4b.png)

* However, this isn't quite what we want. We're shown results by year, instead of day of the week. This can be selected by clicking on the arrow on the `Scheduled Day` pill, selecting “More”, then “Weekday.”
 
  ![No-shows changed to weekday](Images/05-noshow4c.png)

* To display a bar chart instead of a line chart, select "Bar" in the “Marks” section, and add `No-show` to the "Color" in the “Marks” section. 

  ![No-shows by weekday](Images/05-noshow4d.png)

* After adding `No-show` to the "Color" in the “Marks” section, the chart should look like this:

  ![No-shows by weekday and if they were a no-show or not](Images/05-noshow4e.png)

* In the next visualization, students were asked to display the number of individuals with diabetes by gender and across age groups. One way to visualize this is by stacking `Gender` in Rows.

  ![Individuals with diabetes by gender across age groups](Images/05-noshow5a.png)

* The final visualization is very similar to the previous one, visualizing alcoholism instead of diabetes.

  ![Alcoholism by gender across age groups](Images/05-noshow5b.png)

* Send out the [04-Stu_NoShow_Visualization/Solved/no_shows.twbx)](Activities/04-Stu_NoShow_Visualization/Solved/no_shows.twbx) solution for students to refer to later.

* Answer any questions before moving on to the next activity.

</details>



---

### 4. The Ultimate Candy

| Activity Time:       0:25 |  Elapsed Time:      1:35  |
|---------------------------|---------------------------|

<details>
  <summary><strong> 📣 4.1 Instructor Do: Sizing, Coloring, and Labels (0:05)</strong></summary>

* You can use slides 30 - 36 to assist you with this section.

* It’s possible that students have not used the “Marks” section in Tableau yet. Remind them that an overview of the “Marks” section was provided in **Lesson 14.2.2**.  Marks can be used in order to differentiate or add details to a chart's visuals.

    ![The options in the Marks section with Path](Images/06-marks_card1.png)

  * The `Color` modifies the colors of a chart so that elements are colored according to the values passed.

  * The`Size` modifies the sizing of elements so that they are bigger or smaller depending on the values passed.

  * The `Label` places text next to points on a chart that correspond with the values passed.

  * The `Detail` and `Tooltip` act like labels, but they only appear when the cursor hovers over the associated point/element on a chart.

  * The `Path` changes the type of line mark, linear, step, or jump, whereas `Shape` changes the shape based on the values passed. Changing the value of the drop-down will change depending on whether the path or shape is displayed.

    ![The options in the Marks section with Shape](Images/06-marks_card2.png)

* Explain to students that they can drag pills to these marks in order to create visual effects. They will have an opportunity to do just that in the next activity.

* Ask the class the following questions and call on students for the answers:

    * **Q:** Where have we used this before?

    * **A:** The “Marks” section was covered in Lesson 14.2.2. Using the “Marks” section is covered throughout the module.

    * **Q:** How does this activity equip us for the Challenge?

    * **A:** We will need to know how to use the “Marks” section to add detail to our visualizations to complete the Challenge.

    * **Q:** What can we do if we don't completely understand this?

    * **A:** We can refer to the lesson plan and reach out to the instructional team for help.

</details>

<details>
  <summary><strong> ✏️ 4.2 Students Do: The Ultimate Candy (0:15)</strong></summary>

* You can use slides 37 - 38 to assist you with this section.

* Students will now take some time to create charts that compare candies. The charts themselves are quite basic but will be made more complex using the “Marks”.

    ![Winning Chocolate Chart](Images/07-Candy_WinChocolate.png)

* Make sure the students can download and open the [instructions](Activities/05-Stu_UltimateCandy_Marks/README.md) and the [candy-data.csv](Activities/05-Stu_UltimateCandy_Marks/Resources/candy-data.csv) file from the AWS link. 

* Go over the instructions in the README, then divide students into breakout groups of 3-5. They should work on the solution by themselves but can reach out to others in their group for tips.

* Let students know that they may be asked to share and walk through their work at the end of the activity.

</details>

<details>
  <summary><strong> ⭐ 4.3 Review: The Ultimate Candy (0:05)</strong></summary>

* Once time is complete, ask for volunteers to share their solution. Remind them that it is perfectly alright if they didn't complete the activity. 

* To encourage participation, you can ask the students to help you create each chart. 

* If there are no volunteers, open up the solved [ultimate_candy.twbx](Activities/05-Stu_UltimateCandy_Marks/Solved/ultimate_candy.twbx) within Tableau and walk through the application with the class, answering whatever questions students may have.

* The first visualization is a pair of bar graphs that chart the `Winpercent` of each candy:

  ![The winning percent of each candy](Images/07-candy01.png)

  * The bars in the left chart are colored by whether the candy is chocolate flavored.
  * The bars in the right chart are colored by whether the candy is fruity.

* Navigate to the `Data Source` tab and show them that `Chocolate` and `Fruity` columns hold true or false values.

  ![Fruity or chocolate colors are Boolean](Images/07-candy02.png)

* In the chart, the candies that are chocolate flavored can be colored by dragging the `Chocolate` pill to the Color mark.

  ![Coloring bars in the chart that are chocolated](Images/07-candy03.gif)

* The candies that are fruity can be colored by dragging the `Fruity` pill to the Color mark. Tableau automatically colors the bars and creates a legend.

  ![Fruit flavored candies colored](Images/07-candy04.png)

* In the second visualization, a scatterplot is created that plots `Winpercent` against `Sugarpercent` for chocolate flavored candies.

  ![The sugar percentage versus the winning percentage for chocolate flavored candies](Images/07-candy05.png)

* `Chocolate` is dragged to the Colors mark, `Competitorname` is dragged to the Detail mark, and `Pricepercent` is dragged to the Size mark.

  ![Creating the sugar percentage versus the winning percentage chart](Images/07-candy06.gif)

  * This chart provides a handy view of trends.

  * For example, candies with a higher win percent tend to be chocolates (orange), and they tend to be pricier (larger circle size).

* The last visualization is virtually identical to the previous one, except that it compares fruity candies against non-fruity ones.

  ![The sugar percentage versus the winning percentage for fruit candies](Images/07-candy07.png)

  * Overall, fruity candies appear to have a lower `Winpercent` and tend to be less expensive.

* Send out the [05-Stu_UltimateCandy_Marks/Solved/ultimate_candy.twbx](Activities/05-Stu_UltimateCandy_Marks/Solved/ultimate_candy.twbx) solution for students to refer to later.

* Answer any questions before moving on to the next activity.

</details>



---

### 5. Calculations

| Activity Time:       0:20 |  Elapsed Time:      1:55  |
|---------------------------|---------------------------|

<details>
  <summary><strong>🎉 5.1 Everyone Do: Calculations (0:20)</strong></summary>

* You can use slides 39 - 40 to assist you with this section.

* In this activity, students will create calculations and logical statements to enhance their visualizations of motor vehicle accidents in New York City.

* Make sure the students can download and open the [instructions](Activities/06-Evr-Calculations/README.md) and the [vehicle_collisions_nyc.csv](Activities/06-Evr-Calculations/Resources/vehicle_collisions_nyc.csv) file from the AWS link. 

* Go over the instructions with the students and check for understanding.

* Ask for volunteers to help create each visualization. If there are no volunteers, import the solved [vehicle_collisions_nyc.csv](Activities/06-Evr-Calculations/Resources/vehicle_collisions_nyc.csv) dataset into Tableau Public and walk through creating each visualization. 

* For the first visualization, the most dangerous hours for a cyclist, we might consider the hours in which cyclists are injured **or** killed above a certain threshold.

  1. Create a new sheet and drag `Cyclists Injured` and `Cyclists Killed` to the Rows, and drag `Time` to the Columns. This creates a double-line graph. 

    ![Cyclist injured and killed line graph](Images/08-nycaccidents1a.png)

  2. However, this graph doesn't tell us the most dangerous times of the day to be riding. By creating a calculated field, we can define these times of day. 

  3. To create a calculated field, go to `Analysis` -> `Create Calculated Field`, then enter the desired `IF-THEN` statement:
  
    ![Cyclist injured and killed calculation](Images/08-nyc_calculation1.png)

  4. When the newly created pill is dragged to the `Color` mark, the subcategories are automatically colored according to the criteria defined in our `IF-THEN` statement.

    ![Cyclist injured and killed calculation on colors](Images/08-nycaccidents1b.png)

  5. The most dangerous time on each line is not that clear; if we change the line graph to a bar graph, the dangerous times stand out against the less dangerous times. 

    ![Cyclist injured and killed bar graph](Images/08-nycaccidents1c.png)

* For the second visualization, the most dangerous months for a cyclist, we might consider the months cyclists are injured above a certain threshold.

  1. Create a new sheet and drag `Cyclists Injured` to the Rows and `Date` to the Columns. Then, filter on the second "Month" option so you get all the years. 

    ![Cyclist injured for the month line graph](Images/08-nycaccidents2a.png)

    ![Cyclist injured for the month line graph](Images/08-nycaccidents2b.png)

  2. Then, create the calculated field to determine the most and least dangerous months based on the number of injuries. 

    ![Cyclist injured for the month calculation](Images/08-nyc_calculation2.png)

  3. Then, drag the newly created calculated field to the "Colors" and change the line to a bar graph . 

    ![Cyclist injured for the month bar graph](Images/08-nycaccidents2c.png)

* For the last visualization, the most dangerous boroughs for people, we might want to create a calculated field to separate out the boroughs with high numbers of injuries. 

  1. Create a new sheet and drag `Persons Injured` to the Rows and `Borough` to the Columns, and then sort by descending number of injuries. 

    ![People injured in each NYC borough graph](Images/08-nycaccidents3a.png)

  2. Then, create the calculated field to determine the dangerous and safe boroughs based on the number of injuries. 

    ![People injured in each NYC borough calculation](Images/08-nyc_calculation3.png)

  3. Then, drag the newly created calculated field to the "Colors". 

    ![People injured in each NYC borough updated bar graph](Images/08-nycaccidents3b.png)

* Next, have the students create their own visualizations, or, show them how to create the "Most Common Causes of Accidents" and the "Number of Injuries Relative to January 2015" visualizations in the solved [motor_vehicle_accidents.twbx](Activities/06-Evr-Calculations/Solved/motor_vehicle_accidents.twbx) file.

* If time allows, discuss the validity of these visualizations. For example, the visualizations suggest that 5 p.m. to 7 p.m. are the most dangerous hours for a cyclist. What are some possible explanations for this phenomenon? Can we truly conclude that the visualizations are correct?

  * One explanation is that more commuters, including cyclists, are on the road during rush hour. A greater number of cyclists could naturally lead to more accidents, but we cannot necessarily conclude that, relative to other hours, rush hour is more dangerous.

  * In both creating and assessing data visualizations, it is important to consider such confounding factors.

* Send out the [06-Evr-Calculations/Solved/motor_vehicle_accidents.twbx](Activities/06-Evr-Calculations/Solved/motor_vehicle_accidents.twbx) solution for students to refer to later.

* Answer any questions before ending class.

</details>




---

  
### 6. Ending Class 

| Activity Time:       0:05 |  Elapsed Time:      2:00  |
|---------------------------|---------------------------|

<details>
  <summary><strong>📣  6.1 Instructor Do: Review </strong></summary>

* Before ending class, review the skills that were covered today and mention where in the module these skills are used: 
  * Importing data into Tableau was covered in **Lesson 14.1.4**.
  * Learning how to use Tableau and creating basic visuals were covered in **Lessons 14.2.5 - 14.2.7**.
  * An overview of the “Marks” section was covered in **Lesson 14.2.2**. And using the “Marks” section was covered throughout the module.

* Answer any questions the students may have.

</details>





---

© 2021 Trilogy Education Services, LLC, a 2U, Inc. brand.  Confidential and Proprietary.  All Rights Reserved.
