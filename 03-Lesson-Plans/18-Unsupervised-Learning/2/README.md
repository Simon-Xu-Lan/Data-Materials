# Module 18 Class 2: Principal Component Analysis and Hierarchical Clustering

## Overview

Before class, walk through this week's Challenge assignment in office hours. In class, the students will learn about dimension reduction with principal component analysis (PCA) as well as an alternative to the K-means algorithm called hierarchical clustering.

## Learning Objectives

By the end of class, students will be able to:

* Understand how to reduce features or dimensions using PCA.
* Perform PCA on datasets.
* Use hierarchical clustering as alternative to K-means.

- - -

## Instructor Notes

* The activities in this class will complement Lessons **18.5.1: Dimensionality Reduction** through **18.6.4: K-means vs. Hierarchical Clustering**.  The students will benefit from these activities if they‘ve progressed through these lessons, which cover the following concepts, techniques, and tasks:

   * Dimensionality reduction
   * Principal component analysis
   * Mean, variance, and covariance
   * Linear transformations
   * Hierarchical clustering
   * Dendrograms
   
* If you have issues with any of today's activities, you may report it [here](http://tiny.cc/BootCampFeedback).

## Slides

[Unsupervised Learning Day 2](https://docs.google.com/presentation/d/1UCyC1m6R0wLUWpO6VWe_JwsW2W1yADmXN-Dqyvug_pk/edit?usp=sharing)

## Student Resources

If students were unable to download today's [activity resources](https://2u-data-curriculum-team.s3.amazonaws.com/data-viz-online-lesson-plans/18-Lessons/18-2-Student_Resources.zip) from Canvas, please share them with the students.

- - -

## Before Class

### 0. Office Hours

| Activity Time: 0:30       |  Elapsed Time:     -0:30  |
|---------------------------|---------------------------|

<details>
 <summary><strong>📣 Instructor Do: Challenge Instruction Walkthrough</strong></summary>

Let the students know that you’ll walk through the Challenge requirements and rubric during the first few minutes of Office Hours, while also providing helpful tips to ensure they know exactly what they need in order to be successful.

Open the Challenge in Canvas and go through the high-level instructions and requirements with your class. Be sure to check for understanding.

Open the Rubric in Canvas, go through the Mastery column with the class, and show how it maps back to the requirements for each deliverable. Be sure to check for understanding.

Review the following tips to ensure clarity on the Challenge:

For **Deliverable 1: Preprocessing the Data For PCA**, they will use their knowledge of data preparation and preprocessing to format PCA-ready data.

Review the Deliverable 1 section of the [Module 18 Cryptocurrency solution](../../../01-Assignments/18-Unsupervised-Learning/Challenge/crypto_clustering_solution.ipynb) and compare it to the [Cryptocurrency Challenge starter code](../../../01-Assignments/18-Unsupervised-Learning/Resources/crypto_clustering_starter_code.ipynb). Show the students the commented steps where they will add code to complete the Challenge.

Tell the students that much of the code they’ll be adding will involve preparing the data for PCA.

For **Deliverable 2: Reducing Data Dimensions Using PCA**, students will use their knowledge of PCA to reduce the dimensions of the DataFrame to three principal components and place them in a new DataFrame.

Go over the Deliverable 2 section of the [Module 18 Cryptocurrency solution](../../../01-Assignments/18-Unsupervised-Learning/Challenge/crypto_clustering_solution.ipynb) and compare it to the [Cryptocurrency Challenge starter code](../../../01-Assignments/18-Unsupervised-Learning/Resources/crypto_clustering_starter_code.ipynb). Show the students the commented steps where they will be adding code to complete the Challenge.

Scroll through to show the students what the final DataFrame for this deliverable will look like.

For **Deliverable 3: Clustering Cryptocurrencies Using K-means**, they will apply their knowledge of the K-means algorithm and use `hvPlot` to create an elbow curve to find the best value for `k` from the DataFrame created in the last step. Then, they will run the K-means algorithm to predict the `k` clusters of the cryptocurrency data.

Go over the Deliverable 3 section of the [Module 18 Cryptocurrency solution](../../../01-Assignments/18-Unsupervised-Learning/Challenge/crypto_clustering_solution.ipynb) and compare it to the [Cryptocurrency Challenge starter code](../../../01-Assignments/18-Unsupervised-Learning/Resources/crypto_clustering_starter_code.ipynb). Show the students the commented steps where they will be adding code to complete the Challenge.

For **Deliverable 4: Visualizing Cryptocurrencies Results**, they will use their knowledge of scatter plots with Plotly Express and `hvplot` to visualize the distinct groups that correspond to the three principal components created in Deliverable 2; then, they will create a table with all the currently tradable cryptocurrencies using `hvplot.table()`.

Go over the Deliverable 4 section of the [Module 18 Cryptocurrency solution](../../../01-Assignments/18-Unsupervised-Learning/Challenge/crypto_clustering_solution.ipynb) and compare it to the [Cryptocurrency Challenge starter code](../../../01-Assignments/18-Unsupervised-Learning/Resources/crypto_clustering_starter_code.ipynb). Show the students the commented steps where they will be adding code to complete the Challenge.

Encourage your class to begin the Challenge as soon as possible, if they haven’t already, and to use the Learning Assistants channel and the remainder of Office Hours with their instructional team for help as they progress through their work. If they feel like they need context to understand documentation or instructions throughout the week, this is where they can get it.

Open the floor to discussion and be sure to answer any questions they may have about the Challenge requirements before moving on to other areas of interest.

</details>

<details>
 <summary><strong>📣  Instructor Do: Office Hours</strong></summary>

For the remaining time, remind the students that this is their time to ask questions and get assistance from their instructional staff as they’re learning new concepts and working on the Challenge assignment.

Expect that students may ask for assistance with the following:

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

* Open the slideshow and use slides 1-6 to walk through the foundation setting with your class.

* **This Week - Unsupervised Learning:** Talk through the key skills that students will learn this week, and let them know that they are continuing to build on their data analyst skills.

* **Today's Objectives:** Now, outline the concepts covered in today's lesson. Remind students that they can find the relevant activity files in the “Getting Ready for Class” page in their course content.

</details>

<details>
 <summary><strong>🎉 1.2 Everyone Do: Check-In (0:05)</strong></summary>

* Ask the class the following questions and call on students for the answers:

   * **Q:** How are you feeling about your progress so far?

   * **A:** We are adding to our machine learning skill set. It's important to look back and see what we accomplished, and acknowledge that it's a lot! It’s also okay to feel overwhelmed as long as you don’t give up. The more you practice the more comfortable you'll be coding.

   * **Q:** How comfortable do you feel with this topic?

   * **A:** Let's do "fist to five" together. If you are not feeling confident, hold up a fist (0). If you feel very confident, hold up an open hand (5).

</details>



- - -

### 2. Principal Component Analysis (PCA)

| Activity Time:       1:05 |  Elapsed Time:      1:15  |
|---------------------------|---------------------------|

<details>
 <summary><strong> 📣 2.1 Instructor Do: Speed up Machine Learning with PCA (0:15) </strong></summary>

* In this activity, students will learn how to use principal component analysis to speed up machine learning algorithms by reducing the number of features. You may use slides 7-14 to accompany this activity.

* [Ins_PCA.ipynb](Activities/01-Ins_PCA/Solved/Ins_PCA.ipynb)

* Explain to students that PCA is a statistical technique to speed up machine learning algorithms.

  * It does so by reducing the number of input features (or dimensions).

  * The PCA algorithm transforms a large set of variables into a smaller one that contains most of the information from the larger original set.

  * PCA can be quite helpful with enormous datasets, saving both time and computing resources.

* Open [Ins_PCA.ipynb](Activities/01-Ins_PCA/Solved/Ins_PCA.ipynb) in the Jupyter Notebook, demo the code, and highlight the following:

  * Again, we are using the iris dataset, which has four features.

 ![The iris dataset without target class](Images/iris_dataset.png)

 * Before using PCA, we need to standardize the data. Scikit-learn's `StandardScaler` module is used here. The `fit_transform()` method combines training and transforming data into a single step.

 ![Using StandardScaler](Images/using-standardscaler.png)

  * Once the features are standardized, PCA can be used to reduce the number of features in the dataset.

  * A PCA model is created. The `n_components` parameter specifies the final number of features. Here, the number of features is reduced from `4` to `2`.

 ```python
 pca = PCA(n_components=2)
 ```

*Explain to students that the online material will go into more detail about how PCA mathematically works to reduce features while retaining the important information. For the sake of brevity and complexity, we won’t cover it in the live class, but encourage students to spend some time going over it in Canvas.

 * PCA then reduces the dimensions of the scaled dataset with the familiar `fit_transform` method.

 ```python
 iris_pca = pca.fit_transform(iris_scaled)
 ```

* Inform students that PCA reduces the dataset into a smaller set of dimensions called **principal components**.

 * There isn’t a particular meaning assigned to each principal component: the new components are just the two main dimensions of variations that contain most of the information in the original dataset.

* Show students the transformed PCA data:

 ![PCA Data](Images/pca-df.png)

  * This data will be fed into the K-means algorithm, as we have done before.

  * The principal component values bear little resemblance to the original dataset. They can be seen as a reduced representation of the original data.

* Explain that we can assess the amount of information that has been preserved in the PCA dimensionality reduction with the `explained_variance_ratio_` attribute:

 ![Explained variance](Images/explained-variance.png)

  * Here, the first principal component is responsible for `72.77%` of the variance, and the second principal component contains `23.03%` of the variance.

  * Together, the principal components preserve `95.80%` of the information.

  * In other words, a little over 4% of the useful information was lost in the dimensionality reduction performed by PCA.

* Explain that after reducing the dataset, we can continue to perform unsupervised learning with the K-means algorithm:

 ![PCA Elbow Curve](Images/pca-elbow-curve.png)

  * Even though dimensionality reduction led to some loss of information, the elbow curve still suggests a `k` of 3.

  * The K-means algorithm is then used to predict the clusters for the iris data with a `k` of 3.

 ```python
 # Initialize the K-Means model
 model = KMeans(n_clusters=3, random_state=0)

 # Fit the model
 model.fit(df_iris_pca)

 # Predict clusters
 predictions = model.predict(df_iris_pca)
 ```

* Finally, the clusters are plotted; they are now easier to analyze since we have only two features.

 ![Clusters plot](Images/pca01.png)

  * The reduced dataset still splits the dataset into 3 distinct clusters.

* Send out the [solution](Activities/01-Ins_PCA/Solved/) for students to refer to later.

* Answer any questions before moving on.

</details>

<details>
 <summary><strong> ✏️ 2.2 Students Do: PCA in Action (0:20) </strong></summary>

* Next, proceed with the student exercise. In this exercise, students will use PCA to reduce the dimensions of a consumer shopping dataset.

* Open the [Stu_PCA.ipynb](Activities/02-Stu_PCA/Unsolved/Stu_PCA.ipynb) file in Jupyter Notebook and scroll through to display what students will be creating.

* Make sure the students can download and open the [instructions](Activities/02-Stu_PCA/README.md), the [starter code](Activities/02-Stu_PCA/Unsolved/Stu_PCA.ipynb), and the [dataset](Activities/02-Stu_PCA/Resources/shopping_data_cleaned.csv) from the AWS link.

* Go over the instructions with the students and answer any questions before breaking the students out in groups.

* Divide students into groups of 3 to 5. They should work on the solution by themselves but can reach out to others in their group for help.

* Let students know that they may be asked to share and walk through their work at the end of the activity.

</details>

<details>
 <summary><strong> ⭐ 2.3 Review Activity (0:05) </strong></summary>

* Once time is up, ask for volunteers to walk through their solution. Remind them that it is perfectly alright if they didn't finish the activity.

* To encourage participation, you can open the [starter code](Activities/02-Stu_PCA/Unsolved/Stu_PCA.ipynb) and ask the students to help you write the code to standardize the data.

* Continue this process for the remainder of the code.

* If there are no volunteers, open up [solution file](Activities/02-Stu_PCA/Solved/Stu_PCA.ipynb) and review it line by line with the class, answering whatever questions students may have.

* Key points to cover are:

  * First, the features are standardized.

 ```python
 shopping_scaled = StandardScaler().fit_transform(df_shopping)
 print(shopping_scaled[0:5])
 ```

  * We use PCA to reduce the number of dimensions from 4 to 2.

 ```python
 # Initialize PCA model
 pca = PCA(n_components=2)

 # Get two principal components for the data.
 shopping_pca = pca.fit_transform(shopping_scaled)
 ```

 * Transform PCA data to a DataFrame.

 ```python
 # Transform PCA data to a DataFrame
 df_shopping_pca = pd.DataFrame(
    data=shopping_pca, columns=["principal component 1", "principal component 2"]
 )
 df_shopping_pca.head()
 ```

  * The first principal component contains `33.7%` of the variance, and the second principal component contains `26.2%` of the variance. Since we have `59.9%` of the information from the original dataset, it is worthwhile to increase the number of principal components to see whether it will improve the explained variance.

 ![Explained variance with two PCs](Images/explained-variance-2pcs.png)

  * Increasing the number of principal components to three preserves `83.1%` of the information from the original dataset.

 ![Explained variance with three PCs](Images/explained-variance-3pcs.png)

 * The K-means algorithm is run on the principal components data to predict the clusters. A value of `k=5` is used, as this was the number we used in the last activity.

 ```python
 model = KMeans(n_clusters=5, random_state=0)
 model.fit(df_shopping_pca)
 predictions = model.predict(df_shopping_pca)

 # Add the predicted class columns
 df_shopping_pca["class"] = model.labels_
 ```

* If you have Plotly Express installed, show the visualization of the data in 3 dimensions.

 ![Clusters plot](Images/pca-data-plot.png)

  * Each of the 3 axes represents a principal component.

* Explain to students that PCA becomes especially powerful with datasets that have hundreds or even thousands of features. For datasets with up to ten features, PCA can simplify data analysis and visualization.

* Send out the [solution](Activities/02-Stu_PCA/Solved/Stu_PCA.ipynb) for students to refer to later.

* Answer any questions before moving on to the next activity.

</details>

<details>
   <summary><strong> ✏️ 2.4  Everyone Do: PCA (0:25)</strong></summary>

* In this exercise, the students will perform PCA on the Boston Marathon dataset.

* Open up the [solved](Activities/03-Evr_PCA/Solved/BostonMarathonPCA.ipynb) file within Jupyter Notebook and scroll through to show students what they will be working on.

* Make sure the students can download and open the [instructions](Activities/03-Evr_PCA/README.md), the [starter code](Activities/03-Evr_PCA/Unsolved/BostonMarathonPCAUnsolved.ipynb), and the [dataset](Activities/03-Evr_PCA/Resources/marathon_results_2019.csv) file from the AWS link.

* Go over the instructions with the students, then let the students work on their solution for 10 minutes.

* When time is up, open the [starter code](Activities/03-Evr_PCA/Unsolved/BostonMarathonPCAUnsolved.ipynb) and run the cells for parts 1 and 2. Then, scroll down to part 3 and ask students to help you write the code to create a training set.

* Continue this process for the rest of the code.

* If there are no volunteers, open up the [solution](Activities/03-Evr_PCA/Solved/BostonMarathonPCA.ipynb) file and go over the solution with the class, answering whatever questions students may have.

* Key points to cover during this discussion:

  * Point out that we need to reproduce many steps from previous exercises, but we can just copy and paste the appropriate code. Tell students that it's still a good idea to keep all the previous code so we can reproduce the analysis in the final output. Inform students that many times, interviews will have a take-home project, and they will need to turn in an analysis like this for the interview.

  * We create a new training set, and this time we drop `Age` as well since we have our data-driven age groups.

 ```python
 X = df.drop(['Age','Pace'], axis=1)
 ```

  * Again, we need to scale our dataset.

 ```python
 X_scaled = MinMaxScaler().fit_transform(X)
 ```

  * Using PCA, we reduce the number of components to 2.

 ```python
 pca = PCA(n_components=2)
 pca.fit(X_scaled)
 print(pca.explained_variance_ratio_)

 X_pca = pca.transform(X_scaled)
 ```

  * We plot the new scatter plot by PCA component.

 ```python
 df_pca = pd.DataFrame(X_pca, columns=['principal component 1','principal component 2'])
 df_pca.hvplot.scatter(
    x="principal component 1",
    y="principal component 2"
 )
 ```

  * It looks like 2 clusters might make sense, but we'll stick with the elbow method.

 ```
 sse = {}
 K = range(1,10)
 for k in K:
     kmeanmodel = KMeans(n_clusters=k).fit(X_pca)
     sse[k]= kmeanmodel.inertia_

 # Plot
 plt.plot(list(sse.keys()), list(sse.values()))
 plt.xlabel('k')
 plt.ylabel('SSE')
 plt.title('Elbow Method')
 plt.show()
 ```

  * This time, we'll try 4 clusters.

 ```python
 model = KMeans(n_clusters=4, random_state=42).fit(X_pca)
 ```

 ```python
 y_pred = model.fit_predict(X_pca)
 ```

  * Plot the PCA scatter plot again, but this time with points colored according to the predicted cluster.

 ```python
 df_pca["cluster"] = y_pred
 df_pca.hvplot.scatter(
    x="principal component 1",
    y="principal component 2",
    by="cluster"
 )
 ```

  * After attaching the predicted cluster to the original dataset, print out the boxplot of `Pace` broken down by `M/F` and `Cluster`, as well as the summary statistics. Note that in each gender, there are two clusters that overlap strongly. Ask students what breakdowns they came up with for `Pace`. Tell students that there isn’t one correct answer, and interpretation of results like this often requires doing the best we can from what the data gives us.

* Send out the [solution](Activities/03-Evr_PCA/Solved/BostonMarathonPCA.ipynb) for students to refer to later.

* Answer any questions that students may have before moving on to the next activity.

</details>



- - -

### 3. Hierarchical Clustering

| Activity Time:       0:40 |  Elapsed Time:      1:55  |
|---------------------------|---------------------------|

<details>
 <summary><strong> 📣 3.1 Instructor Do: Hierarchical Clustering (0:15) </strong></summary>

* In this activity, students will be introduced to a clustering algorithm called hierarchical clustering. You may use slides 20-26 to accompany this activity.

* Open [eurovision.ipynb](Activities/04-Ins_Hierarchical_Clustering/Solved/eurovision.ipynb) to give an overview of hierarchical clustering.

* Introduce the dataset:

 ![Images/dendro0.png](Images/dendro0.png)

  * Eurovision is an international song contest in which member countries vote on songs submitted by other participating countries.

  * Each row represents how that country voted for other countries.

* Scroll down to the dendrogram and explain the basic ideas behind hierarchical clustering:

 ![Images/dendro1.png](Images/dendro1.png)

  * The tree-like structure seen here is called a dendrogram.

  * Here, each cluster starts at the **bottom** of the dendrogram. Each country is its own cluster.

  * For each cluster, the hierarchical clustering algorithm finds the closest neighbor and merges two clusters into one.

  * This process is repeated until there is a single cluster.

  * A pair of clusters that join at a lower vertical height are closer to each other than a pair of clusters that join at a higher height.

  * A horizontal line at a given height determines the number of clusters. For example, if a horizontal line is drawn slightly below the top of the graph, it will cut across two vertical lines. This means that there are two clusters at that height.

* Explain the following particulars of this dendrogram to the class:

  * Each country is paired with its closest neighboring cluster based on voting patterns.

  * For example, Estonia's closest neighbor is Latvia, and they merge into a single cluster before merging with Lithuania (see labels on bottom left of dendrogram).

  * There appear to be two large clusters: the cluster on the left, in which eastern European countries are more heavily represented, and the one on the right, in which western European countries are more heavily represented.

* Next, open [breast_cancer.ipynb](Activities/04-Ins_Hierarchical_Clustering/Solved/breast_cancer.ipynb) to explain the Python implementation of hierarchical clustering.

* Explain that while hierarchical clustering can be used to examine the relationship of each sample to others, as seen in the Eurovision example, it can also be used to generate cluster labels.

* Explain the code to perform hierarchical clustering and to create a dendrogram:

 ```python
 normalized = normalize(df)
 mergings = linkage(normalized, method='ward')

 dendrogram(mergings,
        leaf_rotation=90,
        leaf_font_size=5)

 plt.show()
 ```

  * Because the mergings are based on the distances between samples, datasets should be standardized or normalized. Here, we use scikit-learn's `normalize` method.

  * The actual clustering is performed here using `scipy`'s `linkage` method. We're using the `ward` method to compute distances between clusters.

  * To generate the dendrogram, SciPy's `dendrogram` method is used:

     * Its first argument, `mergings`, is the linkage matrix that we just generated.

     * The `leaf_rotation` and `leaf_font_size` refer to the text label of each sample. Here, the text is turned vertically, and its font size is set at 5.

* Using slide 25, take a moment to explain some of the linkage methods of hierarchical clustering:

  * Single: the difference between two clusters is defined by the closest distance between two clusters.

  * Complete: the difference between two clusters is defined by the farthest distance between two clusters.

  * `Ward`: this method is based on the squared euclidean distance between clusters. It's the method used in our example, and it is often used as a default.

* Return to the notebook to discuss the findings:

 ![Images/dendro2.png](Images/dendro2.png)

  * A rough rule of thumb is to look for the clusters with the longest branches. Here, at the level of two clusters, there is maximum vertical distance. However, this practice is not always reliable.

 ![Images/dendro04.png](Images/dendro04.png)

* Next, walk through the code that uses hierarchical clustering to generate labels:

 ```python
 cluster = AgglomerativeClustering(n_clusters=2,
                                 affinity='euclidean',
                                 linkage='ward')
 labels = cluster.fit_predict(df2)
 ```

  * The algorithm used here is scikit-learn's `AgglomerativeClustering`, meaning the clustering is performed from bottom to top.

  * `n_clusters`: based on the dendrogram, the number of clusters is set to 2.

  * The `affinity` refers to the metric used to compute the matrix of distances.

  * The cluster labels are generated by the `fit_predict` method.

* Take a moment to explain the `affinity` parameter of scikit-learn's agglomerative clustering.

  * Euclidean: this is the shortest distance between two points.

  * Manhattan: this is the sum of the absolute values of the differences between two points. The path in a Manhattan distance resembles the Manhattan city grid.

* As you close out the activity, point out the following strength and drawback of hierarchical clustering:

  * Strength: Unlike K-means, the number of clusters does not need to be predetermined by the user.

  * Drawback: It slows down exponentially with larger datasets.

* Send out the the [solved eurovision.ipynb](Activities/04-Ins_Hierarchical_Clustering/Solved/eurovision.ipynb), [solved breast_cancer.ipynb](Activities/04-Ins_Hierarchical_Clustering/Solved/breast_cancer.ipynb), and [resources](Activities/04-Ins_Hierarchical_Clustering/Resources) for student to review later.

* Answer any questions before moving on.

</details>

<details>

 <summary><strong> ✏️  3.2 Students Do: Hierarchical Customer Data (0:20) </strong></summary>

* Next, proceed with the student exercise. In this exercise, students will use hierarchical clustering to group and plot customer data.

* Open the [solved file](Activities/05-Stu_Hierarchical_Clustering/Solved/customers.ipynb) in Jupyter Notebook and scroll through to show the students what they will be creating.

* Make sure the students can download and open the [instructions](Activities/05-Stu_Hierarchical_Clustering/README.md), the [starter code](Activities/05-Stu_Hierarchical_Clustering/Unsolved/customers.ipynb), and the [dataset](Activities/05-Stu_Hierarchical_Clustering/Resources/wholesale_customers.csv) from the AWS link.

* Go over the instructions with the students and answer any questions before breaking the students out in groups.

* Divide students into groups of 3 to 5. They should work on the solution by themselves but can reach out to others in their group for help.

* Let students know that they may be asked to share and walk through their work at the end of the activity.

</details>

<details>

 <summary><strong> ⭐  3.3 Instructor Do: Review Activity (0:05) </strong></summary>

* Once time is up, ask for volunteers to walk through their solution. Remind them that it is perfectly alright if they didn't finish the activity.

* To encourage participation, you can open the [starter code](Activities/05-Stu_Hierarchical_Clustering/Unsolved/customers.ipynb) and ask the students to help you write the code to normalize the data.

* Continue this process for the remainder of the code.

* If there are no volunteers, open up [solution](Activities/05-Stu_Hierarchical_Clustering/Solved/customers.ipynb) and go over the solution file line by line with the class, answering whatever questions students may have.

* Key points to cover:

  * After reading in the dataset, it is normalized.

  * Since the normalized data is formatted as an array, it is copied into a new DataFrame.

  * The column names from the original DataFrame are copied over as well.

* Go over the code for hierarchical clustering.

 ```python
 mergings = linkage(normalized, method='ward')

 dendrogram(mergings,
          leaf_rotation=90,
          leaf_font_size=5)
 ```

 * A matrix of distances is generated with the `linkage` function; here, we use the `ward` method.

* Discuss the dendrogram generated by hierarchical clustering.

 ![Images/dendro04.png](Images/dendro04.png)

  * The largest vertical distance is found with two clusters, suggesting that we explore two clusters.

* Next, explain generating cluster labels.

 ```python
 cluster = AgglomerativeClustering(n_clusters=2,
                                 affinity='euclidean',
                                 linkage='ward')
 labels = cluster.fit_predict(df2)
 ```

 * Scikit-learn's `AgglomerativeClustering` method performs essentially the same task as Scipy's `linkage`, but it also allows us to generate predicted labels.

* Finally, discuss the plots.

 ![Images/hierarchical01.png](Images/hierarchical01.png)

 ![Images/hierarchical02.png](Images/hierarchical02.png)

  * Because each plot only uses two of the dataset's features, it should be regarded as a rough approximation, not an accurate representation.

  * However, there do appear to be two reasonably separable clusters.

* Send out the [solution](Activities/05-Stu_Hierarchical_Clustering/Solved/customers.ipynb) for students to refer to later.

* Answer any questions before moving on to the next activity.

</details>



- - -

### 4. Ending Class

| Activity Time:       0:05 |  Elapsed Time:      2:00  |
|---------------------------|---------------------------|

<details>
 <summary><strong>📣  4.1 Instructor Do: Review </strong></summary>

* Before ending class, review the skills that were covered today and mention where in the module these skills are used.
 * Principal component analysis was covered in **Lesson 18.5.2**.
 * Understanding hierarchical clustering was covered in **Lesson 18.6.1**.
 * Running hierarchical clustering was covered in **Lesson 18.6.3**.
 * K-means vs. hierarchical clustering was covered in **Lesson 18.6.4**.

* Answer any questions the students may have.

</details>



- - - 

© 2021 Trilogy Education Services, LLC, a 2U, Inc. brand.  Confidential and Proprietary.  All Rights Reserved.
