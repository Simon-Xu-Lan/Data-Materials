# Module 18 Class 1: Introduction to Unsupervised Machine Learning

## Overview

This week, we will be introducing **unsupervised machine learning**. In this unit, students will learn about unsupervised learning and how it compares to supervised learning.

In today's class, students will learn how to process and prepare data for unsupervised models. The will then be introduced to the K-means algorithm.

## Learning Objectives

By the end of class, students will be able to:

* Understand how unsupervised learning compares to supervised learning
* Prepare and process data for unsupervised learning
* Apply K-means clustering
* Use the elbow curve to determine optimal cluster number

- - -

## Instructor Notes

* The activities in this class will complement Lessons **18.0.1: Using Unsupervised Learning to Discover Unknown Patterns** through **18.4.2: Use the Elbow Curve**. The students will benefit from these activities if they‘ve progressed through these lessons, which cover the following concepts, techniques, and tasks:

    * Supervised learning recap
    * Executing Python files
    * Unsupervised learning: transformation and clustering
    * Preparing Data
    * Preprocessing data with Pandas
    * Data selection
    * Clustering data
    * The K-means algorithm
    * Finding centroids
    * Elbow curves

* If you have issues with any of today's activities, you may report it [here](http://tiny.cc/BootCampFeedback).

## Slides

[Unsupervised Day 1 slideshow](https://docs.google.com/presentation/d/1D0oIi_TtKgbXNPjQ1WCOt97OLuwL5-a_VhYei3TdSzI/edit?usp=sharing)

## Student Resources

If students were unable to download today's [activity resources](https://2u-data-curriculum-team.s3.amazonaws.com/data-viz-online-lesson-plans/18-Lessons/18-1-Student_Resources.zip) from Canvas, please share them with the students.

- - -

## Before Class

### 0. Office Hours

| Activity Time: 0:30       |  Elapsed Time:     -0:30  |
|---------------------------|---------------------------|

<details>
 <summary><strong> 📣 0.1 Instructor Do: Office Hours</strong></summary>

* Before you begin class, hold office hours. Office hours should be driven by students. Encourage students to take full advantage of office hours by reminding them that this is their time to ask questions and get assistance from instructional staff as they learn new concepts.

* Expect that students may ask for assistance with the following:

 * Further review on a particular subject
 * Debugging assistance
 * Help with computer issues
 * Guidance with a particular tool

</details>

- - -

## During Class

### 1. Getting Started

| Activity Time:       0:15 |  Elapsed Time:      0:15  |
|---------------------------|---------------------------|

<details>
 <summary><strong>📣 1.1 Instructor Do: Foundation Setting (0:10)</strong></summary>

* Welcome students to class.

* Direct students to post individual questions in the Zoom chat to be addressed by you and/or your TAs at the end of class.

* Open the slideshow and use slides 1-12 to walk through the foundation setting with your class.

* **Big Picture:** This is an opportunity to zoom out and see the big picture of where they are in the program. Take a moment to mention some real-world examples illustrating the value of what they're learning this week.

* **Program Pointers:** Talk through some of the key logistical things that will help students stay on track. This is an opportunity to speak to what students may need when they're at this particular point of the program.

* **This Week - Unsupervised Learning:** Talk through the key skills students will be learning this week. Let students know that they have just learned about supervised learning, which deals with known outputs. This week, they will use unsupervised learning to deal with unknown outputs.

* **This Week's Challenge:** For this week's Challenge, let the students know that they'll be analyzing cryptocurrency data. The students will need to preprocess the data, reduce data dimensions using principal component analysis (PCA), cluster the data with K-means, and visualize the results.

* **Career Connection:** Let students know how they will be using the skills covered this week throughout their careers. It's important for them to know the "why." Give examples of when they may be used in work or when you have used those skills in your workplace.

* **How to Succeed This Week:** Remind your students that they may have moments of frustration this week as they learn something complex. These moments are great for deepening their knowledge. Use the side material to outline some of the topics that they may find tricky in this module. Consider sharing something about your personal learning journey. It helps students to recognize that everyone starts somewhere and that they are not alone.

* **Today's Objectives:** Now, outline the concepts that will be covered in today's lesson. Remind students that they can find the relevant activity files in the “Getting Ready for Class” page in their course content.

</details>

<details>
 <summary><strong>🎉  1.2 Everyone Do: Check-In (0:05)</strong></summary>

* Ask the class the following questions and call on students for answers:

   * **Q:** How are you feeling about your progress so far?

   * **A:** Let them know that we are starting to build their skillset. It’s also okay to feel overwhelmed as long as you don’t give up.

   * **Q:** How comfortable do you feel with this topic?

   * **A:** Let's do "fist to five" together. If you are not feeling confident, hold up a fist (0). If you feel very confident, hold up an open hand (5).

</details>



- - -

### 2. Intro to Unsupervised Machine Learning

| Activity Time:       0:10 |  Elapsed Time:      0:25  |
|---------------------------|---------------------------|

<details>
 <summary><strong> 📣 2.1 Instructor Do: Introduction to Unsupervised Learning (0:10) </strong></summary>

* In this activity, students will be introduced to unsupervised learning and its most relevant applications. You may use slides 13-32 to accompany this activity.

* Start the presentation by highlighting some differences between supervised learning and unsupervised learning.

| Supervised Learning | Unsupervised Learning |
| ---------------------------------- | ------------------------------------------ |
| Input data is labeled | Input data is unlabeled |
| Uses training datasets | Uses just input datasets |
| **Goal:** Predict a class or value | **Goal:** Determine patterns or group the data |

* Remind your students about the following points from last week’s module on supervised learning:

 * The data was labeled. Each loan sample was labeled as low_risk or high_risk.

 * The dataset was split into training and testing sets.

 * The three supervised models &mdash; resampling, SMOTEENN, and ensemble classifiers &mdash; created predictions, which were tested against the testing set.

* Explain to students some common uses of unsupervised learning:

 * Grouping unlabeled data into distinct clusters (clustering)

 * Detecting unusual data points in a dataset, i.e., anomaly detection

 * Reducing large datasets into smaller datasets while preserving most of the useful information (dimensionality reduction)

* Ask the class how clustering might be used by retail businesses:

 * One possible answer is that it can be used to group customers by shopping habits to create customized offers via email or mobile apps.

* Ask the class how anomaly detection might be used by credit card companies:

 * One possible answer is that it can be used to detect anomalous and potentially fraudulent credit card transactions (by grouping transactions as normal or abnormal).

* Ask the class how dimensionality reduction might be used in organizations with a large volume of data:

 * It can speed up machine learning by reducing the size of large datasets.

* Continue the presentation. Highlight the following:

 * Supervised learning is very helpful at predicting the future based on labeled historical data. However, labeled data is not always available.

 * Unsupervised learning allows us to cluster data to find hidden or unknown patterns in data.

* Explain that customer segmentation is one of the most popular applications of unsupervised learning. It categorizes customers based on their demographic and behavioral traits.

* Explain that with unsupervised learning algorithms, we can group customer-based similarities such as:

 * Customer needs (e.g., a particular product can satisfy some of them)

 * Responses to online marketing channels

 * Buying habits (e.g., best day for buying, weekly spend, etc.)

* Explain to students that customer segmentation is a major revenue driver in leading companies like Netflix and Amazon.

 * 75% of Netflix viewer activity is driven by recommendation ([source](https://www.wired.com/2013/08/qq-netflix-algorithm/)).

 * 35% of Amazon’s sales are generated through their recommendation engine ([source](https://www.martechadvisor.com/articles/customer-experience-2/recommendation-engines-how-amazon-and-netflix-are-winning-the-personalization-battle/)).

 * Netflix’s recommendation system saves the company an estimated $1 billion per year through reduced churn ([source](https://dl.acm.org/citation.cfm?id=2843948)).

* Answer any questions before moving on.

</details>



- - -

### 3. Data Preparation

| Activity Time:       0:55 |  Elapsed Time:      1:20  |
|---------------------------|---------------------------|

<details>
 <summary><strong> 📣 3.1 Instructor Do: Data Preparation for Unsupervised Learning (0:10) </strong></summary>

* In this activity, students will learn how to prepare data for unsupervised learning. You may use slides 33-36 to accompany this activity.

* Explain to the class that they should consider the following data preparation tasks:

 * **Data selection:** Think through what data is going to be used. It is important to consider what is available in the dataset, what is missing, and what can be removed.

 * **Data preprocessing:** Organize the selected data by formatting, cleaning, and sampling it.

 * **Data transformation:** Transform the data to a format that makes it easier to use and store for future use. (e.g., CSV file, spreadsheet, database).

* Open and introduce the [iris dataset](Activities/02-Ins_Data_Prep/Resources/iris.csv) to the students. Explain that they will look at two examples of the same dataset.

 * It has 150 records (rows) of data.

 * Each record lists five attributes of an iris, such as petal length and width, and the species of the iris.

* Next, open [Data_Preparation.ipynb](Activities/02-Ins_Data_Prep/Solved/Data_Preparation.ipynb) and introduce sklearn's built-in iris dataset. Explain that this dataset has already been cleaned up and is ready to use.

 ```python
 from sklearn.datasets import load_iris
 iris = load_iris()
 iris.feature_names
 ```

 * The `load_iris` module is a dataset that comes with the scikit-learn library.

 * Calling `iris.feature_names` returns the names of the features, or columns, of the dataset.

 * Calling `iris.data` returns the iris data, namely the sepal length and width, as well as the petal length and width of each recorded iris.

* Similarly, explain that the labels (in this case, the name of the iris species) are also easily accessible.

 ```python
 iris.target_names
 iris.target
 ```

 * `iris.target_names` lists the names of the three iris species in the dataset: setosa, versicolor, and virginica.

 * `iris.target` comprises the actual labels. Instead of the species being specified as string, they have been encoded numerically: 0 for setosa, 1 for versicolor, and 2 for virginica.

* Remind your students that real-life datasets will usually require data cleaning. Inform them that the next example will require some preprocessing steps.

* Load the iris data CSV file into Pandas.

 ```python
 # Loading data
 file_path = Path("../Resources/iris.csv")
 df = pd.read_csv(file_path)
 df.head(5)
 ```

 * The iris species is listed in the `class` column.

 * The species names can be retrieved with `df['class'].unique()`.

* Next, explain that we can encode the string values in the `class` column into numeric values, just like in the sklearn dataset.

 ```python
 class_dict = {'Iris-setosa': 0, 'Iris-versicolor': 1, 'Iris-virginica':2}
 df2 = df.replace({'class': class_dict})
 ```

 * First, we create a dictionary of the species names and the numerical values we wish to replace them with.

 * Then, we use Pandas's `replace` method to replace the values in the `class` column.

* Highlight to students that the main difference in preparing data for unsupervised learning is that its algorithms don't have any target variable; they only have input features that will be used to find patterns in the data. So, they should take care to select features that could help find those patterns or create groups.

* Answer any question before moving on.

</details>

<details>
 <summary><strong> ✏️ 3.2 Students Do: Understanding Customers (0:20) </strong></summary>

* Next, proceed with the student exercise. In this activity, students will perform data preparation tasks on a dataset about the purchases made by 200 customers on an e-commerce website. You may use slides 37-40 to accompany this activity.

* Some data transformations should be made to the dataset, so ask TAs to assist students if there are any questions about why the following changes are needed.

* **Annual Income:** This feature should be regularized since it is on a different scale than the other features; dividing by `1000` is the simplest solution.

* **Previous Shopper:** The `Previous Shopper` should be transformed to a numerical value; in this case, transforming `Yes` to `1` and `No` to `0` is a feasible solution.

* **CustomerID:** Since this column is not relevant to the clustering algorithm, it should be dropped from the DataFrame.

* Open the [preparing_data.ipynb](Activities/03-Stu_Preparing_Data/Solved/preparing_data.ipynb) and scroll through the notebook to display what they will be creating.

* Make sure the students can download and open the [instructions](Activities/03-Stu_Preparing_Data/README.md), the [preparing_data.ipynb](Activities/03-Stu_Preparing_Data/Unsolved/preparing_data.ipynb), and the [shopping_data.csv](Activities/03-Stu_Preparing_Data/Resources/shopping_data.csv) file from the AWS link.

* Go over the instructions with the students and answer any questions before breaking the students out in groups.

* Divide students into groups of 3 to 5. They should work on the solution by themselves but can reach out to others in their group for help.

* Let students know that they may be asked to share and walk through their work at the end of the activity.

</details>

<details>
 <summary><strong> ⭐ 3.3 Review Activity (0:05) </strong></summary>

* Once time is up, ask for volunteers to walk through their solution. Remind them that it is perfectly alright if they didn't finish the activity.

* To encourage participation, you can open [preparing_data.ipynb](Activities/03-Stu_Preparing_Data/Unsolved/preparing_data.ipynb) and ask the students to answer the first question about column data types.

* Continue this process for the remainder of the code.

* If there are no volunteers, open up [solution](Activities/03-Stu_Preparing_Data/Solved/preparing_data.ipynb) and go over the solution file line by line with the class, answering whatever questions students may have.

* Walk through the solution and highlight the following:

 * Unsupervised learning algorithms only work with numerical data, so it is crucial to check data types to ensure that numerical values were loaded to the DataFrame with the appropriate data type.

 ```python
 df_shopping.dtypes

 CustomerID                 int64
 Previous Shopper          object
 Age                        int64
 Annual Income              int64
 Spending Score (1-100)     int64
 ```

 * All columns but `Previous Shopper` have a numeric data type, so we will only need to encode this column.

 * The `CustomerID` column can be dropped; it is not relevant for clustering since it does not denote any characteristics relevant to customer shopping habits.

 ```python
 df_shopping = df_shopping.drop(columns=["CustomerID"], inplace=True)
 ```

 * Looking for `null` values and duplicate entries is part of any data preprocessing workflow; there are no `null` values or duplicates in this DataFrame, so no additional adjustments are needed.

 * The `Previous Shopper` column is categorical, so it should be transformed into numerical values. Transforming `Yes` to `1` and `No` to `0` is a common practice.

 ```python
 def changeStatus(status):
    if status == "Yes":
        return 1
    else:
        return 0

 df_shopping["Previous Shopper"] = df_shopping["Previous Shopper"].apply(changeStatus)
 ```

 * The `Annual Income` column is on a different scale than the other columns, so this column should be rescaled. Dividing by `1000` is the simplest approach.

 ```python
 df_shopping["Annual Income"] = df_shopping["Annual Income"] / 1000
 ```

 * Finally, the cleaned DataFrame is saved as a `CSV` file for use in the coming activities.

 ```python
   file_path = Path("../Resources/shopping_data_cleaned.csv")
   df_shopping.to_csv(file_path, index=False)
 ```

* Send out the [solution](Activities/03-Stu_Preparing_Data/Solved/preparing_data.ipynb) for students to refer to later.

* Answer any questions before moving on to the next activity.

</details>

<details>
   <summary><strong> ✏️ 3.4 Everyone Do: Boston Marathon Preprocessing (0:20)</strong></summary>

* In this exercise, the students will prepare Boston Marathon data for unsupervised learning.

* Open up the [solved](Activities/04-Evr_Preprocessing/Solved/BostonMarathonPreprocessing.ipynb) file within a Jupyter Notebook and scroll through to show students what they will be doing.

* Make sure the students can download and open the [instructions](Activities/04-Evr_Preprocessing/README.md), the [starter code](Activities/04-Evr_Preprocessing/Unsolved/BostonMarathonPreprocessingUnsolved.ipynb), and the [data file](Activities/04-Evr_Preprocessing/Resources/marathon_results_2019.csv) from the AWS link.

* Go over the instructions with the students, then let them work on their solution for 5 to 7 minutes.

* When time is up, open the [starter code](Activities/04-Evr_Preprocessing/Unsolved/BostonMarathonPreprocessingUnsolved.ipynb) file and ask students to help you write the code to start cleaning the DataFrame.

* Continue this process for the remainder of the code.

* If there are no volunteers, open up the [solution](Activities/04-Evr_Preprocessing/Solved/BostonMarathonPreprocessing.ipynb) file and go over the solution with the class, answering whatever questions students may have.

* Key points to cover during this discussion:

 * The following code converts the time stamps into seconds in two steps.

 ```python
 time_columns = ['5K', '10K', '15K', '20K', 'Half','25K', '30K', '35K', '40K', 'Pace', 'Official Time']
 df[time_columns] = df[time_columns].apply(pd.to_timedelta)

 df[time_columns] = df[time_columns].apply(lambda x: x.dt.total_seconds())
 ```

 * In the step where only nonzero split-time rows are kept, show students that there are multiple ways to take only nonzero rows.

 ```python
 df = df[
    (df['5K'] != 0) &
    (df['10K'] != 0) &
    (df['15K'] != 0) &
    (df['20K'] != 0) &
    (df['Half'] != 0) &
    (df['25K'] != 0) &
    (df['30K'] != 0) &
    (df['35K'] != 0) &
    (df['40K'] != 0)
 ]

 # A more concise method
 #df = df[~(df == 0).any(axis=1)]
 ```

 * The `M/F` column is a string, so it needs to be converted to integers with `LabelEncoder`.

 ```python
 df['M/F'] = LabelEncoder().fit_transform(df['M/F'])
 ```

 * `Age` may have come in as a string, so to be sure it's a numeric value, we convert it with `to_numeric`.

 ```python
 df['Age'] = pd.to_numeric(df['Age'])
 ```

* Point out that part of preprocessing is doing EDA. For example, we expect that `Pace` is perfectly correlated to `Official Time`, since it's just the final time divided by the length of the marathon, but we should always check our assumptions first. A scatter plot is a quick way to see if these two features are correlated.

 ```python
 df.plot(kind='scatter', x='Pace', y='Official Time')
 ```

 * Now, we can subset our training set.

 ```python
 X = df.drop('Pace', axis=1)
 ```

 * Finally, before we can perform a K-means algorithm, we need to scale our data. Once again, we'll use `MinMaxScaler`.

 ```python
 X_scaled = MinMaxScaler().fit_transform(X)
 ```

* Answer any questions students have before moving on.

</details>



- - -

### 4. K-Means Algorithm

| Activity Time:       0:35 |  Elapsed Time:      1:55  |
|---------------------------|---------------------------|

<details>
   <summary><strong> 📣 4.1 Instructor Do: Chicago Marathon K-Means (0:10)</strong></summary>

* The next topic will cover K-means, a popular unsupervised learning algorithm used for clustering data. You may use slides 42-51 - which reference the iris and customers datasets previously used in today's class - to accompany this activity.

* Start by explaining:

 *  The "_k_" in K-means is specifying the number of clusters to find in the data; the K-means algorithm will look for exactly as many clusters as we tell it to find.

 * If we don't know how many clusters we want to look for, we can try many values of _k_ and make an educated guess about the best value.

 * One way to do that is to print the _inertia_ of each model on a line chart and pick the point where the graph makes an "elbow."

* Next, open [ChicagoMarathonKMeans.ipynb](Activities/05-Ins_KMeans/Solved/ChicagoMarathonKMeans.ipynb) in a Jupyter Notebook and go through the code, explaining along the way:


 * This code will plot the _inertia_.

 ```python
 sse = {}
 K = range(1, 10)
 for k in K:
    kmeanmodel = KMeans(n_clusters=k).fit(X_scaled)
    sse[k]= kmeanmodel.inertia_

 # Plot
 plt.plot(list(sse.keys()), list(sse.values()))
 plt.xlabel('k')
 plt.ylabel('SSE')
 plt.title('Elbow Method')
 plt.show()
 ```

 * From this image, 3 or 4 clusters seem to be appropriate. We'll use 3 to start (feel free to run through the code again, changing _k_ to 4).

 ```python
 model = KMeans(n_clusters=3, random_state=42).fit(X_scaled)
 ```

 With a fit model, we can predict values.

 ```python
 y_pred = model.predict(X_scaled)
 ```

 * To continue the analysis, we need to add the calculated clusters to our original DataFrame.

 ```
 df_y = pd.DataFrame(y_pred, columns=['Cluster'])
 combined = df.join(df_y, how='inner')
 combined.head()
 ```

 * One thing that we can check is how the finish times are spread across the groups.

 ```python
 combined.boxplot(['finish'], by=['Cluster'])
 ```

 * Two of the clusters seem to be fairly similar.

 * Finally, we can view the median finish times by division for each cluster.

 ```python
 combined[combined['Cluster'] == 0].groupby('division').median()['finish'].plot()
 combined[combined['Cluster'] == 1].groupby('division').median()['finish'].plot()
 combined[combined['Cluster'] == 2].groupby('division').median()['finish'].plot()
 ```

 * Again, we have similar results from two clusters. However, we get better results than if we just used `k = 2` (feel free to demonstrate this to students). Tell students we might get better results in the next activity, where we bring in PCA.

* Answer any questions before moving on to the next activity.

</details>

<details>
   <summary><strong> ✏️ 4.2 Students Do: K-Means (0:20)</strong></summary>

* Next, proceed with the student exercise. In this exercise, students will apply the K-means algorithm on a different marathon dataset.

* Open the [BostonMarathonKMeans.ipynb](Activities/06-Stu_KMeans/Solved/BostonMarathonKMeans.ipynb) file in a Jupyter notebook and scroll through showing the students what they will be doing.

* Make sure the students can download and open the [instructions](Activities/06-Stu_KMeans/README.md), the [starter code](Activities/06-Stu_KMeans/Unsolved/BostonMarathonKMeansUnsolved.ipynb), and the [data file](Activities/06-Stu_KMeans/Resources/marathon_results_2019.csv) from the AWS link.

* Go over the instructions with the students and answer any questions before breaking the students out in groups.

* Divide students into groups of 3 to 5. They should work on the solution by themselves but can reach out to others in their group for help.

* Let students know that they may be asked to share and walk through their work at the end of the activity.

</details>

<details>
   <summary><strong> ⭐ 4.3 Review: K-means (0:05)</strong></summary>

* Once time is up, ask for volunteers to walk through their solution. Remind them that it is perfectly alright if they didn't finish the activity.

* To encourage participation, you can open the [starter code](Activities/06-Stu_KMeans/Unsolved/BostonMarathonKMeansUnsolved.ipynb), scroll to **Part 2**, and ask the students to help you write the code to create the K-Means model.

* Continue this process for the remainder of the code.

* If there are no volunteers, open up the [solution](Activities/06-Stu_KMeans/Solved/BostonMarathonKMeans.ipynb) and go over it line by line with the class, answering whatever questions students may have.

* Key points to cover are:

 * Start by creating the elbow curve.

 ```python
 sse = {}
 K = range(1,10)
 for k in K:
    kmeanmodel = KMeans(n_clusters=k).fit(X_scaled)
    sse[k]= kmeanmodel.inertia_

 # Plot
 plt.plot(list(sse.keys()), list(sse.values()))
 plt.xlabel('k')
 plt.ylabel('SSE')
 plt.title('Elbow Method')
 plt.show()
 ```

 * Point out that `k=3` seems to be a good choice here.

 ```python
 # Create a KMeans model with 3 clusters
 model = KMeans(n_clusters=3, random_state=42).fit(X_scaled)
 ```

 * With a fit model, predict the values, and add the predicted clusters to the original DataFrame.

 ```python
 # Calculate predicted values.
 y_pred = model.predict(X_scaled)
 ```

 ```python
 # Add predicted values onto the original dataframe
 df_y = pd.DataFrame(y_pred, columns=['Cluster'])
 combined = df.join(df_y, how='inner')
 combined.head()
 ```

 * Go over the box plots of `Official Time` by `Cluster`, and point out that there is a fairly clear division between the clusters, but we might be able to do even better by converting the ages into age groups.

```python
combined.boxplot(['Official Time'], by=['Cluster'])
```

  ![grouped by cluster box plot](Images/grouped_box_plot.png)

 * Print out the summary statistics of ages by sex and predicted cluster.

```python
combined.groupby(['M/F','Cluster']).describe()['Age']
```

 * Tell students that we can use this data to create age breakpoints, especially at the medians, but since the medians take on a relatively narrow range, we can also take the lowest 1st quartile and highest 3rd quartile as breakpoints as well.

 * We'll make a function with nested `elif` statements and then apply them to the data frame.

 ```python
 def age_group(gender, age):
    if gender == 0:
        if age < 29:
            return 0
        elif age < 36:
            return 1
        elif age < 41:
            return 2
        elif age < 45:
            return 3
        elif age < 51:
            return 4
        else:
            return 5
    if gender == 1:
        if age < 33:
            return 0
        elif age < 40:
            return 1
        elif age < 48:
            return 2
        elif age < 53:
            return 3
        elif age < 60:
            return 4
        else:
            return 5
 ```

 * Point out that this step could still be considered preprocessing, even though we're using a machine learning algorithm.

* Send out the [solution](Activities/06-Stu_KMeans/Solved/BostonMarathonKMeans.ipynb) for students to refer to later.

* Answer any questions before ending class.

</details>



- - -

### 5. Ending Class

| Activity Time:       0:05 |  Elapsed Time:      2:00  |
|---------------------------|---------------------------|

<details>
 <summary><strong>📣  5.1 Instructor Do: Review </strong></summary>

* Before ending class, review the skills that were covered today and mention where in the module these skills are used.
 * Preprocessing data was covered in **Lesson 18.2.1** through **Lesson 18.2.6**.
 * Clustering data was covered in **Lesson 18.3.1**.
 * The K-means algorithm was covered in **Lesson 18.3.2**.
 * The elbow curve was covered in **Lesson 18.4.1**.

* Answer any questions the students may have.

</details>



---

© 2021 Trilogy Education Services, LLC, a 2U, Inc. brand.  Confidential and Proprietary.  All Rights Reserved.
