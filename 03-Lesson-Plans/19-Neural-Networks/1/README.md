# Module 19 Class 1: Introduction to Advanced Machine Learning

## Overview

This week, we will be introducing the students to neural networks and deep learning. In this unit, students will compare the machine learning classification and regression models from previous modules with the neural network models used in this module. Then, they’ll use TensorFlow to implement neural networks and deep neural networks across a number of different datasets, including image, natural language, and numerical datasets. 

In today's class, students will review neural networks, the perceptron neural network model, and the components of a basic neural network. Then, they’ll use the TensorFlow Playground to explore the components of a neural network and how each component interacts with others. Finally, they’ll set up Google Colaboratory to execute “cloud-based Jupyter Notebooks” and build their own neural network model. 

## Learning Objectives

By the end of class, students will be able to:

* Compare the traditional machine learning classification and regression models with the neural network models
* Describe the perceptron model and its components
* Understand the concepts of a basic neural network 
* Run cloud-based Jupyter Notebooks with Google Colaboratory
* Implement neural network models using TensorFlow

- - -

## Instructor Notes

* The activities in this class will complement Lessons **19.0.1: The Rise of Machine Learning** through **19.2.3: Train and Test a Basic Neural Network**.  The students will benefit from these activities if they‘ve progressed through these lessons, which cover the following concepts, techniques, and tasks:  

  * Understanding the concept of a neural network
  * Understanding the concept of the perceptron model
  * Using the TensorFlow Playground to understand a neural network and change its performance
  * Installing TensorFlow 
  * Building a basic neural network 
  * Predicting the classification of data from a trained neural network


* If you have issues with any of today's activities, you may report it [here](http://tiny.cc/BootCampFeedback).

## Instructor Prep

* For those who have some experience with machine learning but not with neural network models, we have selected a few online resources for you to consume prior to this week's class. Please take some time to review these materials as they will provide much-needed context for how neural networks function:

  * [But what is a Neural Network?](https://www.youtube.com/watch?v=aircAruvnKk) A fantastic introduction to neural networks and what they do.

  * [Hands-On in the Playground](https://www.youtube.com/watch?v=ru9dXF04iSE):  Interact with TensorFlow Playground step by step.
  
* Make a copy of the [Data Blended Online: Final Group Project Survey](https://docs.google.com/forms/d/1sjy17GNFkOeSvjHH_s17WVYvmv7_Y1v3BCvxLFXJkmE/edit?usp=sharing) and place it in your Google Drive. At the end of class, ask the students to complete the survey so you can make a more informed decision on how to place students in groups based on their topic interest.


## Slides

[Neural Networks and Deep Learning Day 1 slideshow](https://docs.google.com/presentation/d/1XLd5K9N-7c8_2IsxmZNKO-Cfe7jKwfO-d-76I1AliO8/edit?usp=sharing)


## Student Resources

If students were unable to download today's [activity resources](https://2u-data-curriculum-team.s3.amazonaws.com/data-viz-online-lesson-plans/19-Lessons/19-1-Student_Resources.zip) from Canvas, please share them with the students.

- - - 

## Before Class

### 0. Office Hours

| Activity Time: 0:30       |  Elapsed Time:     -0:30  |
|---------------------------|---------------------------|

<details>
  <summary><strong> 📣 0.1 Instructor Do: Office Hours</strong></summary>

* Before you begin class, hold office hours. Office hours should be driven by students. Encourage students to take full advantage of office hours by reminding them that this is their time to ask questions and get assistance from instructional staff as they learn new concepts.

* Expect that students may ask for the following: 

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

* Direct students to post individual questions in the Zoom chat to be addressed by you or your TAs at the end of class.

* Let the students know that they'll be starting their final project next week and you’ll be sending out a link to the **Data Blended Online: Final Group Project Survey** to get each student’s feedback.

* Open the slideshow and use slides 1 - 12 to walk through the foundation setting with your class. 

* **Big Picture:** This is an opportunity to zoom out and see the big picture of where they are in the program. Take a moment to mention some real-world examples that show the value of what they’re learning this week.

* **Program Pointers:** Talk through some of the key logistical things that will help students stay on track. This is an opportunity to speak to what students may need when they're at this particular point of the program. 

* **This Week - Neural Networks and Deep Learning:** Talk through the key skills students will be learning this week. The primary focus of the Day 1 activities is to reinforce the concepts and components of a basic neural network. On Day 2, the activities will dive into building a neural network and optimizing its performance.

* **This Week's Challenge:** For this week's Challenge, let the students know that they'll be creating a binary classifier that is capable of predicting whether applicants will be successful if funded by Alphabet Soup. For this Challenge, they’ll need to import, analyze, clean, and preprocess a charity dataset, and then select, design, and train a binary classification model. Finally, they will optimize the model by modifying the input data and training to achieve a desired model performance.

* **Career Connection:** Let students know how they will use the skills covered this week throughout their careers. It's important for them to know the "why." Give examples of when they may be used in work or when you have used those skills in your workplace. 

* **How to Succeed This Week:** Remind your students that they may have moments of frustration this week as they learn something complex. These moments are great for deepening their knowledge. Use the slide material to outline some of the topics that they may find tricky in this module. Consider sharing something about your personal learning journey. It helps students to recognize that everyone starts somewhere and that they are not alone.

* **Today's Objectives:** Now, outline the concepts that will be covered in today's lesson. Remind students that they can find the relevant activity files in the “Getting Ready for Class” page in their course content. 

</details>

<details>
  <summary><strong>🎉  1.2 Everyone Do: Check-In (0:05)</strong></summary>

* Ask the class the following questions and call on students for answers:

    * **Q:** How are you feeling about your progress so far?

    * **A:** We are continuing to build on your machine learning skill set by learning the concepts of neural networks, building a neural network, and optimizing its performance. It’s okay to feel overwhelmed as long as you don’t give up.

    * **Q:** How comfortable do you feel with this topic? 

    * **A:** Let's do "fist to five" together. If you are not feeling confident, hold up a fist (0). If you feel very confident, hold up an open hand (5).

</details>



- - -

### 2. Introduction to Advanced Machine Learning

| Activity Time:       0:15 |  Elapsed Time:      0:30  |
|---------------------------|---------------------------|

<details>
  <summary><strong>📣 2.1 Instructor Do: Surfing the Neural Net (0:05)</strong></summary>

* You can use slides 13 - 17 to assist you in this activity. 

* Welcome students to class; then, let them know that in our final week of machine learning, we will be focusing on one of the most in-demand skills for any data scientist&mdash;**neural networks**.

* Explain to students that neural networks are a powerful machine learning technique modeled after neurons in the brain.

  * They are used by industry leaders such as Google, Facebook, Twitter, and Amazon to analyze complex datasets.

* Show the students the image of the MNIST dataset:

   ![MNIST example](Images/mnist_dataset.png)

* Point out that neural network models can analyze numerical data, natural voice, text, and even images. One classic neural network example uses a handwriting classification model based on the MNIST database.

  * The MNIST (Modified National Institute of Standards and Technology) dataset contains black-and-white images of handwritten numbers.

  * A neural network can train on each pixel of each image as a scaled value from zero (completely white) to one (completely black). With enough data points, a trained neural network model can classify handwritten numbers with a high degree of accuracy.

* Show the students the example diagram of a neural network:

   ![Neural Network Diagram](Images/nn_diagram.png)

* Mention to students that those who have experience building neural network models tend to get hired faster and at higher salaries than other data scientists.

* Show the students the following diagram plotting the different types of machine learning models.

  ![machine_learning_diagram](Images/machine_learning_diagram.png)

* Remind the students that throughout the past two weeks, we have learned and implemented a number of supervised and unsupervised models.

  * These models range in accuracy and interpretability, and each has their specific use cases.

* Let the students know that this week, we will focus on neural networks and their more complex variant, deep learning models.

  * Just like our previous machine learning models, neural networks have many use cases and can be applied to a wide variety of datasets.

  * By the end of this week, we will be able to implement and optimize neural network models, and we'll compare the performance of neural networks to other supervised and unsupervised machine learning models.

</details>

<details>
  <summary><strong>📣 2.2 Instructor Do: What Is a Neural Network? (0:10)</strong></summary>

* You can use slides 18 - 23 to assist you for this activity. 

* Ask the students if anyone has heard of a **neural network** model.

  * If anyone raised their hand, ask if they could describe what a neural network is.

* Answer by letting the students know that a **neural network** is an advanced form of machine learning that contains multiple layers of **nodes**, which perform individual computations.

  * Inform the students that neural networks were modeled after the human brain; therefore, the nodes in a layer are often referred to as **neurons**.

* Show the students the following example neural network diagram:

   ![example neural network diagram](Images/neural_network_example_dog_cat.png)

* Explain that the layers of **neurons** are connected and weighed against one another until the neurons reach the final outer layer. The outer final layer returns a numerical&mdash;encoded&mdash;categorical result.

* Inform the students that neural networks are particularly useful in data science because they serve multiple purposes:

  * One of the most popular uses for a neural network is as a classification algorithm to determine how to categorize an input.

  * Another popular use for a neural network is as a regression model to predict dependent outputs from independent input variables.

* Point out that neural networks are a great alternative to many of the machine learning models we have learned throughout the course&mdash;logistic regression, random forest, and multiple linear regression.

* Ask the class the following questions and call on students for the answers:

    * **Q:** Where have we used this before?

    * **A:** An overview of a neural network was provided in Lesson 19.1.1.

    * **Q:** How does this activity equip us for the Challenge?

    * **A:** We will need to understand what a neural network is used for to help us complete the Challenge.

    * **Q:** What can we do if we don't completely understand this?

    * **A:** We can refer to the lesson plan and reach out to the instructional team for help.

 * Take a moment to address any questions before moving on to the next activity.


</details>




- - -

### 3. Neural Network Basics

| Activity Time:       0:45 |  Elapsed Time:      1:15  |
|---------------------------|---------------------------|

<details>
  <summary><strong>📣 3.1 Instructor Do: Perceptron, the Computational Neuron (0:10)</strong></summary>

* You can use slides 24 - 42 to assist you in this activity. 

* Reassure students that neural networks may sound intimidating, but in reality they are simply layer after layer of smaller models such as our logistic regression model.

* Inform the students that the original design for computational neurons (and subsequently the neural network) dates as far back as the 1950s.

* You can use **slides 29 - 33** to assist you with this section. 

* Let the students know that at that time, Frank Rosenblatt created the **perceptron model**. The perceptron model is a single neural network unit that mimics the biological neuron by receiving input data, weighing the information, and producing a clear output.

* Show the students the image of the perceptron model:

  ![perceptron model](Images/perceptron_model.png)

* Inform the students that the perceptron model has four major components:

    ![perceptron model input](Images/perceptron_model_input.png)

  * The **input values**, which are typically labelled as *𝜒* (chi) and pronounced "kaai" as in *ki*te. Depending on how many features or variables exist in the dataset, the number of input values will change.

    ![perceptron model weight](Images/perceptron_model_weights.png)

  * The **weight coefficients**, which are applied to each input value to help the machine learning model identify features of interest. The weight coefficients are typically labelled as *w* or omega.

    ![perceptron model bias term](Images/perceptron_bias_term.png)

  * The **bias constant**, which is an additional input typically labelled as *⍵* (omega). The bias term helps to shift the output of the model, which may be necessary for properly training the model.

    ![perceptron model net summary](Images/perceptron_net_summary.png)

  * The **net summary function**, which aggregates all weighted inputs to provide an output value. In this example, the net summary function is a summation.

* You can use **slides 34 - 42** to assist you with the rest of this activity. 

* Emphasize that the perceptron model&mdash;also known as a **linear binary classifier**&mdash;is most commonly used to separate data into two groups.

  * In other words, the perceptron algorithm works to separate and classify the data into two groups using a linear equation. If they can be separated that way, they are considered **linearly separable**.

* Show the students the following image, which compares two datasets. One dataset is linearly separable; the other is not.

  ![linearly versus not-linearly separable](Images/linearly_versus_notlinearly.png)

* Point out to the students that the perceptron model is a form of **supervised machine learning** because we provide the model with input features and parameters.

* Explain to the students that the easiest way to understand how the perceptron model works is by walking through the algorithm step by step.

* Show the students the following image for our perceptron example:

  ![perceptron dataset](Images/perceptron_dataset_1.png)

* Illustrate that in our example, we want to generate a perceptron classification model that can distinguish between purple squares and blue circles.

* Mention to the students that because our model will try to classify values in a two-dimensional space, our perceptron model will use three inputs:

  * *𝜒1* - the _x_ value

  * *𝜒2* - the _y_ value

  * *⍵0* - the bias constant

* Show that the end result of our two-dimensional perceptron model is the net sum function: **⍵0 + 𝜒1⍵1 + 𝜒2⍵2**.

* Explain that as with any untrained machine learning model, the weights and coefficients are arbitrary and oftentimes random.

* Show the students the following image of an untrained perceptron model on our dataset:

  ![perceptron model untrained](Images/perceptron_dataset_2.png)

* Emphasize that the untrained model did a decent job classifying the two groups, but it is not perfect: one of the blue circles was misclassified.

* Show the students the next image:

  ![perceptron model incorrect](Images/perceptron_dataset_3.png)

* Inform the students that the perceptron model will evaluate each data point and determine if the input weights should change. If a data point is classified correctly, the weights will not change. If a data point is misclassified, the weights will move the model closer to the missed data point.

* Show the students the next image:

  ![perceptron model correct](Images/perceptron_dataset_4.png)

* Let the students know that as with other machine learning algorithms and models, perceptron model training continues until one of three conditions is met:

  * The perceptron model exceeds a predetermined performance threshold set by the designer before training. In machine learning, this is quantified by minimizing the loss metric.

    * For example, if we are working with noisy data that cannot be preprocessed or excluded, our model may not be able to exceed a certain level of performance without overfitting. Therefore, we would want to set a training cutoff at the point of model convergence.

  * The perceptron model training performs a set number of iterations determined by the designer before training.

    * For example, if we know roughly how many iterations it takes for a model to achieve desired performance, we can just "set it and forget it" to train over a specific interval.

  * The perceptron model is stopped or encounters an error during training.

    * This will typically be a hardware or power issue as long as our input data goes through cleaning and preprocessing before use. If we set up our model to save itself after a specific number of training iterations, we can resume training immediately.

* Point out that a simple perceptron model is very similar to our basic statistical models. However, the power of the perceptron model comes from its ability to handle multidimensional data, as well as to interact with other perceptron models.

  * As more multidimensional perceptrons are meshed together and layered, a new, more powerful classification and regression algorithm emerges: the neural network.

* Ask the class the following questions and call on students for the answers:

    * **Q:** Where have we used this before?

    * **A:** The perceptron model was covered in Lesson 19.1.2.

    * **Q:** How does this activity equip us for the Challenge?

    * **A:** Understanding the structure, concepts and design of a perceptron model will help us master building neural networks and complete the Challenge.

    * **Q:** What can we do if we don't completely understand this?

    * **A:** We can refer to the lesson plan and reach out to the instructional team for help.

 * Take a moment to address any questions before moving on to the next activity.

</details>

<details>
  <summary><strong>📣 3.2 Instructor Do: Make the Connections in a Neural Network (0:10)</strong></summary>

* You can use slides 43 - 54 to assist you for this activity.

* Explain that the perceptron model can be thought of as a single "neuron." Now that we understand the structure of a single neuron, it is time to understand the structure of a neural network.

* Show the students the following diagram of a neural network:

   ![neural network diagram](Images/neural_network_diagram.png)

* Illustrate to the students that a basic neural network is composed of three layers:

  * An **input layer** of input values (transformed by weight coefficients)

  * A single **hidden layer** of neurons (single neuron or multiple neurons)

  * An **output layer** reports the classification or regression value

* Let the students know that neural networks link together neurons&mdash;just like the three layers above&mdash;to produce a clear, quantitative output.

* Ask the students the following rhetorical question:

  * "If each neuron has its own output, how does the neural network combine each neuron's output into the model's classification or regression output?"

* Inform the students that neural networks use an **activation function** to transform the output of each neuron to a quantitative value. The transformed output is used as an input value for other layers in the neural network model.

* You can use **slides 51 - 54** to assist you with this section. 

* Mention that there are a variety of activation functions that can be used for many specific purposes. However, most neural networks will use one of the following activation functions:

  * The **linear function** transforms the output into the coefficients of a linear model (the equation of a line).

  * The **sigmoid function** is identified by a characteristic S curve. It transforms the output to a range between 0 and 1.

    ![sigmoid example](Images/sigmoid_example.png)

  * The **tanh function** is also identified by a characteristic S curve; however, it transforms the output to a range between -1 and 1.

    ![tanh example](Images/tanh_example.png)

  * The **rectified linear unit (ReLU) function** returns a value from 0 to infinity, so any negative input through the activation function is 0. It is the most used activation function in neural networks due to its computational simplicity and effectiveness, but it might not be appropriate for simpler models.

    ![relu example](Images/relu_example.png)

  * The **leaky ReLU** function is a "leaky" alternative to the ReLU function, whereby the negative input values will return very small, nonzero, negative values.

    ![leaky relu example](Images/leaky_relu_example.png)

* At this point, we have looked at all of the components of a neural network model. Now, it is time to explore how the components of a neural network model interact.


* Ask the class the following questions and call on students for the answers:

    * **Q:** Where have we used this before?

    * **A:** The basic components of a neural network model &mdash; the hidden layers and activation functions &mdash; were covered in Lesson 19.1.3.

    * **Q:** How does this activity equip us for the Challenge?

    * **A:** Understanding the basic components of a neural network model will help us master building neural networks and complete the Challenge.

    * **Q:** What can we do if we don't completely understand this?

    * **A:** We can refer to the lesson plan and reach out to the instructional team for help.

 * Take a moment to address any questions before moving on to the student activity.

</details>

<details>
  <summary><strong>🎉 3.3 Everyone Do: Playing in TensorFlow Playground (0:15)</strong></summary>

* You can use slides 55 - 60 to assist you in this activity.

* In this next activity, we will explore all the components of a neural network and how each component interacts with others using a teaching application known as the **TensorFlow Playground**.

* Before you start, mention that **TensorFlow** is a neural network and machine learning library for Python that has become an industry standard for developing robust neural network models.

* TensorFlow developed its playground application as a teaching tool to "demystify the black box" of neural networks.

  * TensorFlow provides a working simulation of a neural network as it trains on a variety of different datasets and conditions.

* Inform the students that as a bonus, we can also use TensorFlow Playground to test different configurations of our neural network models &mdash; essentially an abstract form of our **model -> fit -> predict** workflow.

* Remind students that regardless of what machine learning model or technology we use, we follow the same general modelling workflow across all of data science:

  * Decide on a model, and create a model instance.

  * Split into training and testing sets, and preprocess the data.

  * Train/fit the training data to the model.

  * Evaluate the model for predictions and transformations.

* As we progress through the week and experiment with different hyperparameters and configurations, encourage students to try them out ahead of time within TensorFlow Playground.

* Slack out the link to the [TensorFlow Playground](https://playground.tensorflow.org/#activation=sigmoid&batchSize=10&dataset=gauss&regDataset=reg-plane&learningRate=0.03&regularizationRate=0&noise=0&networkShape=1&seed=0.10587&showTestData=false&discretize=true&percTrainData=50&x=true&y=true&xTimesY=false&xSquared=false&ySquared=false&cosX=false&sinX=false&cosY=false&sinY=false&collectStats=false&problem=classification&initZero=false&hideText=false&discretize_hide=true&regularization_hide=true&learningRate_hide=true&regularizationRate_hide=true&percTrainData_hide=true&showTestData_hide=true&noise_hide=true&batchSize_hide=true) to the students.

  ![TF Playground Basic Page](Images/tf_playground_1.png)

* Go over the following components of the playground:

  * The **input data** is located on the left-hand side of the page

    ![TF Playground Input](Images/tf_playground_2.png)

  * The **input features and layer structure** are located in the "Features" section of the page. For this example, we will use *x1* and *x2* for our *x* and *y* values. We can add and subtract neurons using the plus and minus buttons above the neurons. As more neurons are added, each is responsible for keeping track of different weights.

    ![TF Playground Features](Images/tf_playground_3.png)

  * The output of the neural network is visualized in the "output" section of the page. In the output of TensorFlow Playground, we are most concerned about the "Test Loss" function: the better the model performs, the lower the test-loss value.

    ![TF Playground Output](Images/tf_playground_4.png)

  * The **simulation parameters** are found at the top of the page. There are many parameters to tweak and test, such as "learning rate," "activation," and "regularization". However, for our purposes, we will only concentrate on the "activation" and "problem type" parameters.

    ![TF Playground Parameters](Images/tf_playground_5.png)

  * The **simulation controls** are found to the left of the simulation parameters, along with the **epoch counter**. Each epoch is a single training iteration in TensorFlow machine learning training. By pressing the play button, we allow the model to simulate epochs until we press stop.

    ![TF Playground Controls](Images/tf_playground_6.png)

* Once you have finished covering the different features of the TensorFlow Playground, let the students know that they are ready to start simulating their neural network models.

* For the first simulation, we will try to classify two groups using the x1 and x2 features and one neuron.

  * Does this example sound familiar? If it does, that's because it's our previous perceptron model!

* Alongside the students, run the model using the sigmoid function for roughly 100 epochs. Reassure students that they do not need to stop the training at *exactly* 100 epochs.

* Point out that the model's test loss was less than 0.01, which means the model is capable of correctly classifying both groups with high precision.

* Ask the students to rerun their models but use a different activation function.

  * "Did your model training behave differently?" "Why or why not?"

* For the next simulation, we will change our activation function from sigmoid to tanh and train the model through 100 epochs.

* Alongside the students, run the `tanh` simulation through 100 epochs.

* Let the students know that the `tanh` function performs even better than `sigmoid` in approximately the same number of iterations because `tanh` transforms the values between -1 and 1, which makes the changes more dramatic.

* For the final simulation, we will add more neurons to the classification simulation. In this case, we will add two more neurons for a total of three neurons in the hidden layer.

* Ask the students to think about what will happen to our model training as we add more neurons to our model. Will training get faster? Will our model be more accurate?

* Alongside the students, run the multineuron model until the test-loss metric reaches 0.001. Ask the students "approximately how many epochs will it take?"

* Point out to the students that by adding two more neurons while using the `tanh` function, the characteristics of the dataset are much easier to identify. In this case, we were able to achieve the same model performance of our single-neuron model in roughly 33 epochs.

* **Time permitting:** Allow the students an additional 5-10 minutes of "free play" to explore the functionality of the TensorFlow Playground. Encourage them to see what happens when they tweak different parameters.

* Ask the class the following questions and call on students for the answers:

    * **Q:** Where have we used this before?

    * **A:** The TensorFlow Playground was covered in Lesson 19.1.3.


* Be sure to answer any students' questions before moving on.

</details>

<details>
  <summary><strong>📣 3.4 Instructor Do: Set up Google Colab (0:05)</strong></summary>

* You can use slides 61 - 64 to assist you in this activity.

* Now that the students understand enough basic neural network concepts, you will walk through how to program a neural network.

* Mention that TensorFlow can be picky about what version of Python it works with, as well as what modules need to be installed, so we will use Google Colab to run our notebooks in the cloud.

* Navigate to [Google Colaboratory](https://colab.research.google.com/notebooks/welcome.ipynb), then point out the following:

  * We will use **cloud-based notebooks** to run TensorFlow.

  * Google Colaboratory, or Colab, notebooks are Google-hosted notebooks.

  * These cloud-based notebooks allow for easy installation of Spark and the use of cloud-computing power.

* Students will need a Google account to use them. If they do not have one already, encourage them to sign up for one.

* Once a Google account is set up, navigate to [Google drive](https://www.google.com/drive/) and select *Go to Google Drive*.

  ![go to google drive](ColabImages/google_go_to_google_drive.png)

* After you have navigated to Google Drive, click the “New” button and select “Folder” to create a new folder. Refer to the following screenshots. Name the folder “DataClassNotebooks.”

  ![new google folder](ColabImages/google_new.png)

* Navigate to the new folder. Once in the notebook, we’ll need to connect (download) our Google Colab application by following these steps:

  1. Click “New.”
  2. Scroll down to “More” and expand the dropdown menu.
  3. At the bottom of the menu, click “Connect more apps.”

  ![connect apps](ColabImages/google_add_colab.png)

  4. Type “colab” in the top-right search field and press Enter to search for the Colaboratory application.

  ![search colab](ColabImages/google_connect-colab.png)

  5. Click the “Connect” button to download the Colaboratory application.

* Create a Colab Notebook by clicking “New” followed by “More,” and then select “Colaboratory.”

  ![launch colab notebook](ColabImages/google_create-notebook.png)

* A new tab will launch with a new notebook. The functionality is very similar to using Jupyter Notebook, except now everything is hosted online.

* Notebooks can be uploaded directly to Colab. Follow the steps to upload the [WorkThroughNN.ipynb](Activities/02-Evr_WorkThroughNN/Solved/WorkThroughNN.ipynb) file.

  1. From the Colab notebook you just opened, click **File** then **Upload Notebook**.

  ![upload notebook](ColabImages/google_upload_notebook.png)

  2. Drag the [WorkThroughNN.ipynb](Activities/02-Evr_WorkThroughNN/Solved/WorkThroughNN.ipynb) file into the box to upload.

* **Note:** When you upload notebooks, the location in Google Drive will default to a folder called **Colab Notebooks**. But, you can move them to another folder if you wish.

</details>

<details>
  <summary><strong>📣 3.5 Instructor Do: Understanding the TensorFlow Neural Network Structure (0:05)</strong></summary>

* You can use slides 65 - 70 to assist you as you walk through this activity.

* In Colab, run the first cell of `WorkThroughNN.ipynb` and emphasize that there are a number of smaller modules within the TensorFlow 2.0 library that make it even easier to build machine learning models.

* For our purposes, we'll use the Keras module to help build our neural networks, going over the following:

  * Keras contains multiple classes and objects that can be combined to design a variety of neural network types.

  * These classes are order dependent, which means that depending on what Keras objects are used (and in what order), the behavior of the neural network model will change accordingly.

  * For a basic neural network, we will use two Keras classes:
  
    * The **Sequential class** is a linear stack of neural network layers where data flows from one layer to the next. This class is what we simulated in the TensorFlow Playground.

    * The generalized **Dense class** allows us to add layers within the neural network.

* For the Sequential model, we will add multiple Dense layers that will act as our input, hidden, and output layers.

* For each Dense layer, we'll define the number of neurons and activation functions.

* Finally, once we have completed the Sequential model design, we will apply the same scikit-learn **model -> fit -> predict/transform** workflow we have used previously.

* Ask the class the following questions and call on students for the answers:

    * **Q:** Where have we used this before?

    * **A:** The Keras module and the two Keras classes, Sequential and Dense, were covered in Lesson 19.2.1.


* Be sure to answer any students' questions before moving on to the next section and student activity.

</details>



- - -


### 4. Hello, Neural Network World

| Activity Time:       0:40 |  Elapsed Time:      1:55  |
|---------------------------|---------------------------|

<details>
  <summary><strong>🎉 4.1 Everyone Do: Work Through a Neural Network Workflow (0:15)</strong></summary>

* You can use slides 71 and 72 to assist you with starting this activity.

* In this activity, students will build their first neural network model in TensorFlow using parameters and steps that have not been covered in the module. 

* Reassure students that we will review each step in detail so that they will feel comfortable implementing and tweaking the neural network models on their own.

* Make sure the students can download and open the [WorkThroughNN.ipynb](Activities/02-Evr_WorkThroughNN/Unsolved/WorkThroughNN.ipynb) file from the AWS link.

* Make sure the students have connected to Google Colab, and then have them upload the `WorkThroughNN.ipynb` file.

* **Note:** Have the students code alongside you as you walk through the activity.

* As you walk through the activity, go over the following for each step:

* The first step to implementing a basic neural network is to import our dependencies in Python. Open a notebook and run the following block of code.

  ```python
  # Import our dependencies
  import pandas as pd
  import matplotlib as plt
  from sklearn.datasets import make_blobs
  import sklearn as skl
  import tensorflow as tf
  ```

* The next step is to create our dummy data using scikit-learn's *make_blobs* method. *make_blobs* is used to create values for a sample dataset. For our purposes, we'll use *make_blobs* to create 1000 samples with two features that are linearly separable.

* Point out that our two-feature dataset is also known as our _x_- and _y_-values.

* Run the following code block that generates and visualizes our dummy data:

  ```python
  # Generate dummy dataset
  X, y = make_blobs(n_samples=1000, centers=2, n_features=2, random_state=78)

  # Creating a DataFrame with the dummy data
  df = pd.DataFrame(X, columns=["Feature 1", "Feature 2"])
  df["Target"] = y

  # Plotting the dummy data
  df.plot.scatter(x="Feature 1", y="Feature 2", c="Target", colormap="winter")
  ```

   ![make_blobs example](Images/make_blobs_example.png)

* **Q:** Ask the students what the next step in the process will be. 

* **A:** We need to separate our dataset into training and test datasets. This is done using scikit-learn's *train_test_split* method.

* First, run the following code block that splits our dummy data into training and test datasets:

  ```python
  # Use sklearn to split dataset
  from sklearn.model_selection import train_test_split
  X_train, X_test, y_train, y_test = train_test_split(X, y, random_state=78)
  ```
* Next, let the students know that we need to prepare the dataset for our neural network model. Emphasize that &mdash;as with any machine learning algorithm&mdash;it is crucial to normalize or standardize our numerical variables to ensure that our neural network does not focus on outliers and can apply proper weights to each input.

* Let the students know that in most cases, as the input variables are normalized to the same scale, the neural network model will become more stable, and it will get better at "generalizing," or making predictions on new data.

* **Q:** Ask the students what the next steps are in the preprocessing steps of a machine learning pipeline. 

* **A:** We create the pipeline with `StandardScaler()` and then fit or train the pipeline using the `fit()` method; then, we scale the data with the `transform()` method.  

* Run the following code block that normalizes our dummy data:

  ```python
  # Create scaler instance
  X_scaler = skl.preprocessing.StandardScaler()

  # Fit the scaler
  X_scaler.fit(X_train)

  # Scale the data
  X_train_scaled = X_scaler.transform(X_train)
  X_test_scaled = X_scaler.transform(X_test)
  ```

* Now that our dataset is preprocessed, we are ready to build the neural network in Python. To create the neural network in our notebook, run the following code block to create the Sequential model:

  ```python
  # Create the Keras Sequential model
  nn_model = tf.keras.models.Sequential()
  ```

* Demonstrate that the `nn_model` object will store the entire architecture of our neural network model. Next, we must add our layers to the Sequential model.

   ![neural network input and hidden](Images/neural_network_in_hidden.png)

* Point out that the Keras module simplifies the process of building our layers by combining the input layer with the first hidden layer. Therefore, all we need to concentrate on are three parameters:

  1. The **units** parameter indicates how many neurons we want in the hidden layer. For the first neural network, we will use one.

  2. The **activation** parameter indicates which activation function to use. We’ll use the ReLU activation function to allow our hidden layer to identify and train on nonlinear relationships in the dataset.

  3. The **input_dim** parameter indicates how many inputs will be in the model. In this case, we will have two.

* Run the following code block that creates the first Dense layer:

  ```python
  # Add our first Dense layer, including the input layer
  nn_model.add(tf.keras.layers.Dense(units=5, activation="relu", input_dim=2))
  ```

* The next step is to add the output layer. Because we are trying to build a neural network classification model, we want the activation function of the output layer to be the **sigmoid** activation function to produce a probability output.

* Run the following code block, which produces the output Dense layer:

  ```python
  # Add the output layer that uses a probability activation function
  nn_model.add(tf.keras.layers.Dense(units=1, activation="sigmoid"))
  ```

* Now that we have added our layers to the Sequential model, we can double-check our model structure by executing the following code using the summary method:

  ```python
  # Check the structure of the Sequential model
  nn_model.summary()
  ```

   ![Basic Neural Network Summary](Images/basic_nn_summary.png)

* Next, we’ll need to compile and train the model. Depending on the function of the neural network, we will need to compile and train the neural network model with a specific **loss metric**, **optimization function**, and **evaluation metric**.

* Reassure students that TensorFlow and Keras have many parameters to tweak the performance, but most basic classification and regression models use the same parameters.

* Run the following code block, which compiles and trains the basic neural network model. For our purposes, understanding `binary_crossentropy` loss and the `adam` optimizer are outside the scope of this class. As a rule of thumb, whenever we make a classification neural network, we will always use a `binary_crossentropy` loss. For all of our models, we will always use the `adam` optimizer. The `metrics` parameter is used to print a performance metric at the end of each epoch so that we can judge how well the model is doing during training.

  ```python
  # Compile the Sequential model together and customize metrics
  nn_model.compile(loss="binary_crossentropy", optimizer="adam", metrics=["accuracy"])

  # Fit the model to the training data
  fit_model = nn_model.fit(X_train_scaled, y_train, epochs=100)
  ```

* Emphasize that we now have a trained neural network model, and the next step is to test the performance of our neural network to ensure that our model does not need retraining.

* Run the following code block that visualizes the model's training loss over 100 epochs:

  ```python
  # Create a DataFrame containing training history
  history_df = pd.DataFrame(fit_model.history)

  # Increase the index by 1 to match the number of epochs
  history_df.index += 1

  # Plot the loss
  history_df.plot(y="loss")
  ```

   ![basic nn loss](Images/basic_nn_loss.png)

* Run the following code block that visualizes the model's predictive accuracy over the same timeframe:

  ```python
  # Plot the accuracy
  history_df.plot(y="accuracy")
  ```

   ![basic nn accuracy](Images/basic_nn_accuracy.png)

* The final step of our neural network workflow is to evaluate the performance of the trained model against the test dataset. When it comes to a classification model, we want our neural network to have a predictive accuracy as close as possible to 100%, or 1.0.

* Run the following code that evaluates the test loss and predictive accuracy of the model on our testing dataset:

  ```python
  # Evaluate the model using the test data
  model_loss, model_accuracy = nn_model.evaluate(X_test_scaled,y_test,verbose=2)
  print(f"Loss: {model_loss}, Accuracy: {model_accuracy}")
  ```

   ![basic nn performance](Images/basic_nn_performance.png)

* Indicate that by looking at the performance of our model, we can see that our trained basic neural network was able to classify every test data point correctly. Although perfect model performance is ideal, more complex datasets and models may not be able to achieve 100% accuracy.

* Emphasize that it is important to establish model performance thresholds before designing any machine learning model. Depending on the type of data and the use case, we may have to recreate and retrain a model using different parameters or training/test data &mdash; or even look to use a different model entirely.

* Ask the class the following questions and call on students for the answers:

    * **Q:** Where have we used this before?

    * **A:** Building a basic neural network was covered in Lesson 19.2.2, and training the model was covered in Lesson 19.2.3.

    * **Q:** How does this activity equip us for the Challenge?

    * **A:** We will need to know how to build and train a neural network to complete the Challenge.

    * **Q:** What can we do if we don't completely understand this?

    * **A:** We can refer to the lesson plan and reach out to the instructional team for help.

* Be sure to answer any student questions before moving on to the next student activity.

</details>

<details>
  <summary><strong>✏️ 4.2 Students Do: Build Your Own Neural Network Model (0:15)</strong></summary>

* You can use slides 73 and 74 to introduce this activity.

* In this activity, students will implement their own basic classification neural network model using the TensorFlow Keras module. In addition, they will create their own dummy data, split the data into training and test sets, and normalize the data using scikit-learn.

* Make sure the students can download and open the [instructions](Activities/03-Stu_BYONNM/README.md) and the [BYO_Neural_Network_starter.ipynb](Activities/03-Stu_BYONNM/Unsolved/BYO_Neural_Network_starter.ipynb) file from the AWS link.

* Go over the instructions with the students and answer any questions before breaking the students out in groups. 

* Divide students into groups of 3-5. They should work on the solution by themselves, but they can talk to others in their group to get tips.

* Let students know that they may be asked to share and walk through their work at the end of the activity.

</details>

<details>
  <summary><strong>⭐ 4.3 Review: Build Your Own Neural Network Model (0:05)</strong></summary>

* Once time is up, ask for volunteers to walk through their solution. Remind them that it is perfectly alright if they didn't finish the activity. 

* To encourage participation, you can open the [BYO_Neural_Network_starter.ipynb](Activities/03-Stu_BYONNM/Unsolved/BYO_Neural_Network_starter.ipynb) file in Jupyter Notebook or Google Colab and ask the students to help you complete each part.

* If there are no volunteers, open up the solved [03-Stu_BYONNM/BYO_Neural_Network.ipynb](Activities/03-Stu_BYONNM/Solved/BYO_Neural_Network.ipynb) within Jupyter Notebook or Google Colab and go through the code line by line with the class. 

* Inform the students that the `make_blobs()` method has a new parameter that we haven't used before, `cluster_std`. This parameter allows us to change the variability in our training dataset. In this case, we increased the variability so that the datasets would overlap.

* Point out that since the data overlaps, the dataset is not (perfectly) linearly separable.

  ![BYO nn make blobs scatter plot](Images/BYO_nn_make_blobs.png)

* Emphasize that no matter how many neurons we provide the model, the neural network will never be able to achieve 100% classification. This is due to some data points being indistinguishable by only *x* and *y* coordinates.

  ![BYO nn performance evaluation](Images/BYO_nn_performance.png)

* Send out the [03-Stu_BYONNM/BYO_Neural_Network.ipynb](Activities/03-Stu_BYONNM/Solved/BYO_Neural_Network.ipynb) file for students to refer to later.

* Answer any questions before ending class.

</details>

<details>
  <summary><strong>📣 4.4 Instructor Do: Debrief on Neural Networks (0:05)</strong></summary>

* You can use slides 76 - 81 to assist you with this activity.

* Inform the students that after today they should be capable of building a neural network model that can classify any two groups that are linearly separable.

* However, emphasize that today we have only scratched the surface of neural network model capabilities.

* Do a quick overview of the workflow of creating a neural network. 

  * Remind students that regardless of what machine learning model or technology we use, we follow the same general workflow:

    1. Decide on a model, and create a model instance.  

    2. Split into training and testing sets
  
    3. Preprocess the data.

    4. Train/fit the training data to the model.

    5. Evaluate the model for predictions and transformations.

  * When creating a neural network, we use two Keras classes, `Sequential` and `Dense`. 
    * `Sequential` is a linear stack of neural network layers where data flows from one layer to the next.
    * `Dense` allows us to add layers within the neural network.

* In the **dense class**, we add *at least* one input layer where we define the activation function, and we add an output layer that uses a probability activation function.

  * Then, we:
    * Create a summary to get the structure of the `Sequential` model.
    * Compile the `Sequential` model.
    * Fit the model to the training data with a defined number of epochs. 
    * Evaluate the model using the test data.

* Let the students know that in our next class, we will start to look at more complex nonlinear datasets and how to handle them by making more robust models. Additionally, we will learn how to preprocess real-world data for use in a neural network model.

* Once again, encourage students to use the TensorFlow Playground to help visualize any of the features of our neural network models, especially how model performance changes as the input data becomes more complicated.

* Be sure to answer any outstanding student questions before ending class.

</details>



- - - 

### 5. Ending Class 

| Activity Time:       0:05 |  Elapsed Time:      2:00  |
|---------------------------|---------------------------|

<details>
  <summary><strong>📣  5.1 Instructor Do: Review </strong></summary>

* Send out the **Data Blended Online: Final Group Project Survey** link from your Google Drive and ask the students to complete the survey.

* Before ending class, review the skills that were covered today and mention where in the module these skills are used: 
  * An overview of a neural network was provided in **Lesson 19.1.1**.
  * The perceptron model was covered in **Lesson 19.1.2**.
  * The basic components of a neural network model were covered in **Lesson 19.1.3**.
  * The TensorFlow Playground was covered in **Lesson 19.1.3**.
  * The Keras module and the two Keras classes, Sequential and Dense, were covered in **Lesson 19.2.1**.
  * Building a basic neural network was covered in **Lesson 19.2.2**, and training the model was covered in **Lesson 19.2.3**.

* Answer any questions the students may have.

</details>



---

© 2021 Trilogy Education Services, LLC, a 2U, Inc. brand.  Confidential and Proprietary.  All Rights Reserved.
