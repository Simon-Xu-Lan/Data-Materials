# Module 16 Class 2: ETL with Amazon Web Services

## Overview

Before class, walk through this week's Challenge assignment in office hours. In class, the students will get introduced to Amazon Web Services, or AWS. They will learn how to store data on AWS Simple Storage Service, or S3, and use Postgres on their Relational Database Services, or RDS. Students will also learn how to monitor costs and shut down services to not accrue anything on top of the free-tier plan. Today's lesson will have students following along with you a bit more than usual as they get acquainted with Amazon Web Services.

## Learning Objectives

By the end of class, students will be able to:

* Create a database in AWS RDS
* Create buckets and load objects into S3
* Connect to the RDS with pgAdmin and perform Create, Read, Update, Delete (CRUD) operations.
* Use AWS for ETL

- - -

## Instructor Notes

* The activities in this class will complement Lessons **16.7.1: Evaluate Amazon Web Services** through **16.9.3: Check AWS billing**.  The students will benefit from these activities if they‘ve progressed through these lessons, which cover the following concepts, techniques, and tasks:

   * Using AWS
   * Creating a Relational Database in AWS
   * Connecting with pgAdmin to an RDS instance
   * Storing data on AWS S3
   * Retrieving data from S3 and performing ETL to load into an RDS instance.
   * Managing AWS billing.
   
* If you have issues with any of today's activities, you may report it [here](http://tiny.cc/BootCampFeedback).

## Slides

[Big Data Day 2 slideshow](https://docs.google.com/presentation/d/1n0qYPal80wOcijbQu83ge6E4y9Clu5J-BNSdmxDzW4Y/edit#slide=id.gab17893448_0_2766)

## Student Resources

If students were unable to download today's [activity resources](https://2u-data-curriculum-team.s3.amazonaws.com/data-viz-online-lesson-plans/16-Lessons/16-2-Student_Resources.zip) from Canvas, please share them with the students.

- - -

## Before Class

### 0. Office Hours

| Activity Time: 0:30       |  Elapsed Time:     -0:30  |
|---------------------------|---------------------------|

<details>
 <summary><strong>📣 Instructor Do: Challenge Instruction Walkthrough</strong></summary>

Let the students know that you’ll walk through the Challenge requirements and rubric during the first few minutes of Office Hours, while also providing helpful tips to ensure that they know exactly what they need to do in order to be successful.

Open the Challenge in Canvas and go through the high-level instructions and requirements with your class. Be sure to check for understanding.

Open the Rubric in Canvas, go through the Mastery column with the class, and show how it maps back to the requirements for each deliverable. Be sure to check for understanding.

Review the following tips to ensure clarity on the Challenge:

For **Deliverable 1: Perform ETL on Amazon Product Reviews**, they will apply their knowledge of the cloud and ETL process to use PySpark to load a customer review dataset into four separate DataFrames that match the table schema. Finally, they will upload those DataFrames into the RDS.

Go over the [Module 16 database schema](../../../01-Assignments/16-Big-Data/Challenge/challenge_schema.sql) to demonstrate what the tables in the RDS will look like. Then, go over the [Module 16 Amazon ETL solution](../../../01-Assignments/16-Big-Data/Challenge/Amazon_Reviews_ETL_solution.ipynb) and compare it to the [Module 16 Amazon ETL starter code](../../../01-Assignments/16-Big-Data/Resources/Amazon_Reviews_ETL_starter_code.ipynb). Show the students the commented steps where they will be adding code to complete the Challenge.

For **Deliverable 2: Determine Bias of Vine Reviews**, they will use their knowledge of PySpark, Pandas, or SQL to determine if there is any bias toward reviews that were written as part of the Vine Program, which are paid reviews. They will determine if having a Vine review makes a difference in the percentage of 5-star reviews.

Go over the [PySpark Vine solution](../../../01-Assignments/16-Big-Data/Challenge/PySpark_Vine_Review_Analysis_solution.ipynb), the [Pandas Vine solution](../../../01-Assignments/16-Big-Data/Challenge/PySpark_Vine_Review_Analysis_solution.ipynb), and the [SQL Vine solution](../../../01-Assignments/16-Big-Data/Challenge/PySpark_Vine_Review_Analysis_solution.ipynb) to show them the different ways they can solve this challenge.

For **Deliverable 3: A Written Report on the Analysis**, they will write a report that summarizes that analysis performed in Deliverable 2. The report will include 3 sections:

1. An overview of the analysis

2. An description of the results using bulleted lists and images of DataFrames to address the following questions:

 * How many Vine and non-vine reviews were there?
 * How many Vine reviews were 5 stars? How many non-Vine reviews were 5 stars?
 * What percentage of Vine reviews were 5 stars? What percentage of non-Vine reviews were 5 stars?

3. A summary that states if there is any positivity bias for reviews in the Vine program. Use the results of their analysis to support the statement. Then, propose additional analysis that could be done with the dataset to support your statement.

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

* **This Week - Big Data:** Talk through the key skills that students will learn this week, and let them know that they are continuing to build on their data analyst skills.

* **Today's Objectives:** Now, outline the concepts covered in today's lesson. Remind students that they can find the relevant activity files in the “Getting Ready for Class” page in their course content.

</details>

<details>
 <summary><strong>🎉 1.2 Everyone Do: Check-In (0:05)</strong></summary>

* Ask the class the following questions and call on students for the answers:

   * **Q:** How are you feeling about your progress so far?

   * **A:** We are adding to our Python skill set. It's important to look back and see what we accomplished, and acknowledge that it's a lot! It’s also okay to feel overwhelmed as long as you don’t give up. The more you practice, the more comfortable you'll be coding.

   * **Q:** How comfortable do you feel with this topic?

   * **A:** Let's do "fist to five" together. If you are not feeling confident, hold up a fist (0). If you feel very confident, hold up an open hand (5).

</details>



- - -

### 2. Creating an AWS Relational Database

| Activity Time:       0:15 |  Elapsed Time:      0:25  |
|---------------------------|---------------------------|


<details>
 <summary><strong> 🎉 2.1 Everyone Do: Create a PostgreSQL Database in RDS (0:15)</strong></summary>

* In this activity, you will have the class follow along to create a PostgreSQL database in RDS. You may use slides 7-19 to accompany this activity.

* **Important!** Send out the disclaimer for [AWS Free Tier](Activities/00-AWS_Free_Tier/AWS-Free-Tier.pdf) services prior to class. Take some time at the beginning of class to explain that, although we are only using free-tier services in class, students should review this documentation in order to avoid accidentally incurring charges. **Note**: If the free trial for your personal AWS account has expired, it may be best to create a new account that has access to all free-tier options.

* Students can follow this activity along with a PDF guide. Send it out: [AWS_RDS_guide.pdf](Supplemental/AWS_RDS_guide.pdf)

* Send out the following link to [AWS Free Tier](https://aws.amazon.com/free/) and ask students to create a Free Tier account.

* Explain to students that today's class will utilize Amazon Web Services. Everything used in class will be available under Amazon's Free Tier program, but students should be careful not to choose any options that have associated costs. Students should also delete their RDS databases after class so that no further costs are incurred. We will cover the steps for deleting RDS databases at the end of class.

* Encourage students to follow along with the process of creating an RDS instance. It takes a few minutes after creation for the instance to get up and running, so you’ll have some time to troubleshoot any issues that students may run into.

* **Note:** AWS is constantly changing their UI, so some of the screenshots may not sync up. If that's the case, please file a bug report so this can be updated!

* Start by logging in to the AWS Management Console. Once you're logged on, click on the nine dots next to "Services", from the dropdown menu select "Database", and the select "RDS". Or, you can type "RDS" in the search bar. 

  ![AWS database options - select RDS](Images/aws_database_options.png)

* Click **Create database** from the **Create database** section to the right. This button will take you to the **Engine options** page, which brings up a menu of different relational databases.

* **Note:** AWS may have a different screen than the one pictured below. If this is the first time using the service, the orange **Create database** will still be on the right.

  ![create_db_button](Images/create_db_button.png)

 **Note:** There may be an option to create a database with Amazon Aurora, which is a paid database. We will not be using this in today's lesson.

* Make sure the **Standard create** option is checked in the first box.

  ![standard create](Images/standard_create.png)

* Select **PostgreSQL** and select version PostgreSQL 12.10-R1 or earlier, and then under **Templates**, select **Free tier**.


  ![Select a PostgreSQL version 12.10-R1 or earlier with free_tier.png](Images/postgres_select-free_tier.png)

  * **Note** that the version version for free tier may be different from what is pictured.

* Fill out the fields under **Settings**. Use **myPostgresDB** as the database instance identifier and **root** as the master username.

 **Note**: We recommend sticking to these names today for consistency, but the database instance identifier and master username can take any name in the future.

* Uncheck the **Auto generate password** box. Enter a password and be sure to record it somewhere. The other settings will be accessible in the future, but the password will not.

   ![db settings](Images/db_settings.png)

* Leave the settings for **DB instance class** as the default values.

* Under the **Storage** box, uncheck the box next to **Enable storage autoscaling** and leave the rest of the options as the default values.

   ![rds storage options](Images/rds_create_storage.png)

* Under **Connectivity**, select **Yes** under the **Public accessibility** option. Explain that this does not mean that everyone can access the database, as a password is still required, but it allows connections from outside sources like pgAdmin. Leave the rest of the options as the default values.

   ![make rds publicly accessible](Images/rds_create_connectivity.png)

* Under **Additional configuration**, click the down arrow and make the database name **my_data_class_db** (use this name for the sake of consistency. In the future, any name can be used). Then, uncheck the boxes next to **Enable automatic backups**, **Enable Performance Insights**, and **Enable auto minor version upgrade**. Leave the rest of the settings as the default values.

   ![rds additional configuration](Images/rds_create_add_config_1.png)

   ![rds additional configuration](Images/rds_create_add_config_2.png)

* Click **Create Database** followed by **View DB Instance details** to navigate to the instance console page. The database creation on AWS's end will take anywhere from 10 to 15 minutes.


</details>



- - -

### 3. Storage with AWS S3

| Activity Time:       0:20 |  Elapsed Time:      0:45  |
|---------------------------|---------------------------|


<details>
 <summary><strong> 📣 3.1 Instructor Do: AWS S3 Intro (0:05) </strong></summary>

* In this activity, you will introduce the AWS file storage system. You may use slides 20-25 to accompany this activity.

* Go through the slideshow and explain the following:

 * Simple Storage Service, or S3, is Amazon's cloud file-storage service that uses key-value pairs. Files are stored on multiple servers and have a high rate of availability.
 * S3 uses *buckets* to store files, which are similar to computer folders or directories. Buckets can contain additional folders and files. Each bucket must have a unique name.

 * S3 has fine-grained control over files, such as read and write permissions. Buckets can assign individual access or total public access.

* Answer any questions before moving on to the next activity.

</details>

<details>
 <summary><strong> 🎉 3.2 Everyone Do: Cloud Storage with S3 (0:15) </strong></summary>

* In this activity, students will learn how to upload a file to S3 and make it publicly available to download.

* Start by sending out the [S3_guide.pdf](Supplemental/S3_guide.pdf) to students.

* Explain the following points:

 * AWS's S3 is a cloud-based file-storage service.

 * Files are stored on multiple servers, providing redundancy for data.

 * Amazon guarantees an uptime, or availability, of over 99.99% for S3 files.

 * On S3, files are organized by buckets.

 * The S3 bucket structure is somewhat similar to a GitHub repository, which also holds files and folders.

 * Each S3 bucket must have a URL that is unique across AWS.

 * An S3 bucket can contain files, but it cannot contain another bucket.

 * In this case, the region precedes `amazonaws.com`, followed by the bucket name and the filename.

   ![Images/s300.png](Images/s300.png)

 * S3 provides a high level of control over the files. At both the bucket and file levels, it is possible to control read-and-write access for different individuals and organizations.

* Tell students to follow along for the rest of the activity.

* Go to **console.aws.amazon.com** and select **S3** under **Storage**.

  ![s3 console](Images/s3_console.png)

* Click **Create bucket**.

  ![create bucket](Images/create_bucket.png)

* Create a bucket name and choose the region.

* **Note:** The bucket name must be unique across all existing bucket names in Amazon S3. Buckets cannot be renamed or created inside of another bucket.

* Leave the region as the default&mdash;
for example, `US East (N. Virginia)`. Changing the region will change the object URL used in all examples today.

  ![naming bucket](Images/naming_bucket.png)

* Under **Block Public Access setting for this bucket**, uncheck the **Block all public access** option and check the box to acknowledge the change.

  ![allow public bucket access](Images/allow_public_access.png)

* Multiple [security breaches](https://securityboulevard.com/2018/01/leaky-buckets-10-worst-amazon-s3-breaches/) have been caused by unsecured S3 buckets.

* Public access is denied by default; for our ease of use, we will allow public access, but for production-ready storage, it's best to limit access to an as-needed basis TODO: link to privileges.

* The rest of the options can be left as the default values.

* **Tags** are user-defined key-value pairs of information that can help keep track of buckets.

* Scroll to the bottom and click **Create bucket**.

  ![final bucket creation](Images/final_create_bucket.png)

* You will be redirected to the main S3 page; click on the bucket you just created.

* We'll now upload an image file to the newly created bucket. Click the bucket name, then click **Upload**. This will direct you to a new page where you can add files or folders to your bucket.

 * Click the **Add files** box, which will allow you to upload local files.

    ![add files](Images/add_files.png)

 * Optionally, you can drag in files.

 * Once the files have been added, scroll down and click **Upload**.

 * After the upload succeeds, click **CLOSE**.

* You will now see your file in the bucket; however, even though we allowed public access to the bucket, the default permission setting for each new file is to deny access to everyone, so it needs to be changed.

* Select the box next to the file, then click **Actions** and select **Make public**.

  ![make object public](Images/make_object_public.png)

* From the next screen, click **Make public**.

* Then, click close on the new screen.

* Your file will now be publicly available. To confirm, click on the file to open the **Object overview** page.

* To confirm, click the **Object URL**. If everything is correct, you will be able to download the file.

  ![object url](Images/object_url.png)

* You will now be able to publicly access your file!

* **Note:** You will always have the ability to remove public access.

* Answer any questions before moving on to the next activity.

</details>



- - -

### 4. AWS with pgAdmin

| Activity Time:       0:25 |  Elapsed Time:      1:10  |
|---------------------------|---------------------------|

<details>
 <summary><strong> 📣 4.1 Instructor Do: PostgreSQL on RDS Introduction (0:05)</strong></summary>

* First, make sure that everyone has a database to use. Database creation was initiated at the beginning of class. Students whose databases are not yet running should follow along with a partner until their database is available.

* In this activity, students will learn how to connect to their RDS instance from pgAdmin in order to interact with the database. You may use slides 27-35 to accompany this activity.

* Explain the following about the new RDS database:

 * RDS stands for relational database service. This is what Amazon uses to host a variety of relational databases in the cloud.

 * These databases can have different dialects, such as MySQL, PostgreSQL, and Amazon's own Aurora database.

 * The database that was created at the beginning of class uses PostgreSQL.

* Navigate to the DB instance in the console created earlier. There will be a lot of information available, but we'll use only a few points of interest. Go over the console page, explaining these key points:

 * The **Summary** section shows what kind of database the instance is and whether it is available.

   ![db summary](Images/db_summary.png)

 * The database metrics can largely be ignored for now.

 * The **Connectivity** tab lists the endpoint, port, and security groups associated with the instance. The endpoint will be used to connect to the database.

   ![db connection](Images/db_connection.png)

 * The rest of the tabs contain more information about the instance, such as backups and logs, but students will not need to concern themselves with this for class.

* Answer any question before moving on to the next activity where everyone will get up and running with pgAdmin and RDS.

 </details>

<details>
 <summary><strong> 🎉 4.2 Everyone Do: RDS PostgreSQL and pgAdmin with CRUD (0:20)</strong></summary>

* In this activity, students will connect pgAdmin to the RDS instance and perform CRUD operations. You may use slides 36-55 to accompany this activity.

* Send out the [RDS_pgAdmin_guide.pdf](Supplemental/RDS_pgAdmin_guide.pdf), which students can use to follow along.

* Make sure everyone has the pgAdmin 4 UI installed. Direct students who do not have it installed to the [pgAdmin download page](https://www.pgadmin.org/download/) to download the appropriate version for their operating system.

* Open up the pgAdmin UI. Explain the following to students:

 * pgAdmin can connect to a cloud-based database, such as AWS, as well as local databases.

 * pgAdmin offers a visual interface for managing data.

* Encourage students to follow along to connect their RDS instance.

* Log in to the AWS console and navigate to **RDS** under **Database**.

  ![RDS console](Images/rds_console.png)

* Navigate to **Instances** in the **Resources** section.

  ![instance_menu.png](Images/instance_menu.png)

* Go to the database created earlier, `mypostgresdb`.

* Navigate to the **Security group rules** section on the right.

* Click the security group for type **CIDR/IP - Inbound**.

  ![security_inbound](Images/security_indbound.png)

* This will navigate to a new page. Follow these steps to give the database access to all inbound traffic:

 * From the management console, navigate to the **Inbound rules** tab on the bottom part of the screen, and then click **Edit inbound rules**. This will bring up a menu to set rules for the security group.

    ![inbound_edit](Images/inbound_edit.png)

 * Change the Source to **Anywhere** and click **Save rules**. The RDS instance will now accept a connection from anywhere. This isn't completely open to the world because the endpoint, username, and password are still needed to connect.

     ![ip_source](Images/ip_source.png)

* Navigate back to the instance console and find your endpoint in the **Connectivity & security** tab.

  ![db connection](Images/db_connection.png)

* Open pgAdmin, right-click on **Servers**, and then go to **Create - Server**. Then, take the following steps to create a connection to the AWS RDS instance.

* Under the **General** tab, enter the server name as **my_aws_postgres_rds**.

  ![server name](Images/general_tab.png)

* Under the **Connection** tab, do the following:

 * Enter the endpoint in the **Hostname/address** field. This is unique to the instance.

 * Enter `postgres` in the **Maintenance** database field. This is the default for all Postgres RDS instances.

 * Enter the username in the **Username** field: in this case, `root`.

 * Enter the password that was created for your RDS instance.

 * Check the box next to **Save password**.

* Click **Save**. If all information is entered correctly, this will set up the connection and not return an error.

   ![connection tab](Images/connection_tab.png)

* Have the TAs verify that every student has a working connection in pgAdmin. Since the class should be using the same username and DB name, the biggest issue should be passwords.

* Once students have successfully connected to the RDS instance, send out the [schema.sql](Activities/02-Evr_RDS_CRUD/Solved/schema.sql).

* Before running the code in pgAdmin, explain the following:

 * The four basic functions of persistent data storage are create, read, update, and delete (CRUD).

 * This schema consists of the first part of CRUD, create.

 * The schema will create the tables. The insertion creates the data.

 * A foreign key is used in the `patients` table to reference the `doctor` table.

* Create a new database named `medical`, open a query tool, and then run the schema. This creates two tables and uploads the data.

* Send out and open [query.sql](Activities/02-Evr_RDS_CRUD/Solved/query.sql). Run through the queries one at a time, explaining the following points:

 * The read functions of a database are run with `SELECT` statements.

    ```sql
    -- Read tables
    SELECT * FROM doctors;

    SELECT * FROM patients;
    ```

 * An error will occur after running the first `INSERT`. This is because the `doctor_id` key 22 does not exist in the `doctor` table.

    ```sql
    -- Inserting with invalid foreign key
    INSERT INTO patients(id, doctor_id, health_status)
    VALUES
    (6, 22, 'sick');
    ```

 * The second `INSERT` statement will run because the foreign key is located in the `doctor` table.

    ```sql
    -- Inserting with valid foreing key
    INSERT INTO patients(id, doctor_id, health_status)
    VALUES
    (6, 1, 'sick');
    ```

 * The update functions are run with `UPDATE`.

    ```sql
    -- Update rows
    UPDATE doctors
    SET taking_patients = FALSE
    WHERE id = 1;

    UPDATE patients
    SET health_status = 'healthy'
    WHERE id = 1;
    ```

 * The delete functions are run with `DELETE`.

    ```sql
    -- Delete row
    DELETE FROM patients
    WHERE id = 1;
    ```

* Send out the [solution files](Activities/02-Evr_RDS_CRUD/Solved/) for students to refer to later.

* Answer any questions before moving on.
</details>



- - -

### 5. ETL with AWS

| Activity Time:       0:30 |  Elapsed Time:      1:40  |
|---------------------------|---------------------------|

<details>
 <summary><strong> 📣 5.1 Instructor Do: ETL with S3, PySpark, and RDS (0:10)</summary></strong>

* In this activity, you will show students how to combine S3 and RDS from AWS to perform ETL with PySpark. You may use slides 56-60 to accompany this activity.

* Before navigating to AWS, open up pgAdmin and navigate to the AWS connection on the left-hand side and create a database called `my_data_class_db` within our RDS instance.

* Open the AWS console and navigate to S3 under **Storage**.

* Use the previously created bucket and upload [user_data.csv](Activities/03-Ins_ETL_S3_RDS/Resources/user_data.csv) and [user_payment.csv](Activities/03-Ins_ETL_S3_RDS/Resources/user_data.csv), making sure they are made public, as we did in the previous file upload.

* Return to pgAdmin and run [schema.sql](Activities/03-Ins_ETL_S3_RDS/Solved/schema.sql) in the `my_data_class_db` RDS database. Review the schema and explain the following:

 * The schema defines three unique tables.

 * Each table is normalized and represents, or models, different data.

 * This schema is only being used to create and simulate a production database.

 * The ETL process will need to `extract` the necessary data from the CSVs, `transform` it, and then `load` the data into these tables.

* Open [etl_s3_rds](Activities/03-Ins_ETL_S3_RDS/Solved/ins_etl_s3_rds.ipynb) in Colab. Update `<bucket name>` with the name of the bucket you just created. **Note:** Some buckets will add the location to the object URL, e.g., `https://s3.us-east-2.amazonaws.com/<bucket name>/user_data.csv`. If an error is returned, grab the object URL from the file and use that instead. Go through the code, explaining the following:

 * Colab needs to install a Postgres driver in order for the notebook to load our end result in an RDS. Then, it will store the driver into the Spark application.

    ```python
      !wget https://jdbc.postgresql.org/download/postgresql-42.2.16.jar

      from pyspark.sql import SparkSession
      spark = SparkSession.builder.appName("CloudETL").config("spark.driver.extraClassPath","/content/postgresql-42.2.16.jar").getOrCreate()
    ```

 * The Colab notebook reads in the file from S3 and stores it in a PySpark DataFrame. The   argument `inferSchema` will assign the correct data types; otherwise, everything will be returned as a string.

   ```python
   from pyspark import SparkFiles
   # Load in user_data.csv from S3 into a DataFrame
   url = "https://<bucket name>.s3.amazonaws.com/user_data.csv"
   spark.sparkContext.addFile(url)

   user_data_df = spark.read.option('header', 'true').csv(SparkFiles.get("user_data.csv"), inferSchema=True, sep=',')
   # Or, user_data_df = spark.read.csv(SparkFiles.get("user_data.csv"), sep=",", header=True, inferSchema=True)
   user_data_df.show(10)
   ```

* Pulling this file from S3 is part of the `extract` portion of the ETL process.

* The PySpark DataFrame will be used to help `transform` the data.

* The next step is to merge the two DataFrames before beginning the cleanup process.

* In this case, part of the `transform` step in the ETL process is to clean the data and remove duplicate or incomplete entries. This can be accomplished with `dropna()` in Pandas.

* The next step creates three new DataFrames that store the information needed to populate the existing tables in the production database. The DataFrame columns should match the table column names.

* Refer back to the schema for the three tables that were created earlier: `active_user`, `billing_info`, and `payment_info`.

* To push the DataFrames up to the database, the mode is set to `append`, the URL is set, and a configuration with the database details is stored in a dictionary.

* PySpark then uses the configuration dictionary to connect to RDS and writes the DataFrame contents to the database.

  ```python
  # Append DataFrame to active_user table in RDS
  mode = "append"
  jdbc_url="jdbc:postgresql://<endpoint>:5432/my_data_class_db"
  config = {"user":"root", "password": "<password>", "driver":"org.postgresql.Driver"}
  clean_user_df.write.jdbc(url=jdbc_url, table='active_user', mode=mode, properties=config)
  ```

* The queries in [query.sql](Activities/03-Ins_ETL_S3_RDS/Solved/query.sql) can be used with pgAdmin to check that data has successfully loaded to their tables.

* Send out the [solution files](Activities/03-Ins_ETL_S3_RDS/) for students to refer to later.

* Answer any questions before moving on to the next activity.

</details>

<details>
 <summary><strong> ✏️ 5.2 Student Do: ETL with S3, PySpark, and RDS (0:15)</summary></strong>

* Next, proceed with the student exercise. In this exercise, students will use S3, RDS, and PySpark to perform an ETL process of their own. You can use slides 60-63 to accompany this activity.

* Open the [schema.sql](Activities/04-Stu_ETL_S3_Colab/Solved/schema.sql) file to show the student what schema they will need to match with the data to upload into an RDS database.

* Make sure the students can download and open the [instructions](Activities/04-Stu_ETL_S3_Colab/README.md) and the [starter code](Activities/04-Stu_ETL_S3_Colab/Unsolved/stu_etl_s3_rds.ipynb) from the AWS link.

* Go over the instructions with the students and answer any questions before breaking the students out in groups.

* Divide students into groups of 3 to 5. They should work on the solution by themselves but can reach out to others in their group for help.

* Let students know that they may be asked to share and walk through their work at the end of the activity.

 </details>

<details>
 <summary><strong> ⭐ 5.3 Review Activity (0:05)</summary></strong>

* Once time is up, ask for volunteers to walk through their solution. Remind them that it is perfectly alright if they didn't finish the activity.

* To encourage participation, you can open the [starter code](Activities/04-Stu_ETL_S3_Colab/Unsolved/stu_etl_s3_rds.ipynb) and ask the students to help you write the code to load in a file from S3.

* Continue this process for the remainder of the code.

* If there are no volunteers, open up [stu_etl_s3_rds.ipynb](Activities/04-Stu_ETL_S3_Colab/Solved/stu_etl_s3_rds.ipynb) and go over the solution file line by line with the class.

* Before walking through the code, emphasize that students are already familiar with most of the processes used in the activity. The new ETL process involves extracting data from S3, transforming the data with PySpark, and loading the data into RDS.

* Explain to students that the first requirement of the activity is to upload the CSV file to S3.

   ![Images/etl01.png](Images/etl01.png)

 * Students should already have an existing bucket, but they are free to create a new one.

 * If a student asks why we're uploading and downloading the same file, respond that we're assuming that the data is already stored in the cloud.

 * The AWS resources used fall well below the free-tier threshold. However, as a safety measure, it is best to clean up resources by deleting them after use. AWS does not cap resource usage and will auto-scale if needed. If usage ever goes beyond the free tier, you will be charged for those resources.

* In Colab, upload the unsolved Jupyter Notebook file:

  ![Images/colab00.png](Images/colab00.png)

* The first two Colab cells install Spark and start a SparkSession.

* Explain that the next cell reads in the data source from S3:

  ```python
  from pyspark import SparkFiles
  # Load in employee.csv from S3 into a DataFrame
  url = "https://<bucket name>.s3.amazonaws.com/employee.csv"
  spark.sparkContext.addFile(url)

  df = spark.read.option('header', 'true').csv(SparkFiles.get("employee.csv"), inferSchema=True, sep=',', timestampFormat="mm/dd/yy")
  df.show(10)
  ```

 * You will have to replace the bucket name.

 * The `timestampFormat` argument reads in the date columns in the CSV, which are originally in string format, and formats them as `timestamp` columns in the Spark DataFrame.

* Preview the first 10 rows of the DataFrame:

  ![Images/colab03.png](Images/colab03.png)

 * The `DOB`, `Hire Date`, and `Modified` columns are formatted as timestamps.

 * The reformatting will enable insertion of this data into the SQL database with the proper data types.

* Open the [SQL schema](Activities/04-Stu_ETL_S3_Colab/Resources/schema.sql):

  ```sql
  CREATE TABLE employee_personal_info (
      employee_id INT PRIMARY KEY NOT NULL,
      email TEXT,
      gender TEXT,
      hire_date DATE,
      dob DATE
  );

  CREATE TABLE employee_password (
      employee_id INT PRIMARY KEY NOT NULL,
      password TEXT
  );
  ```

* Contrast the desired data output of the SQL table schema with the current input seen in the DataFrames.

  * The DataFrames have multiple unnecessary columns.

  * The column names in the SQL tables are lowercase.

* Pause for a moment to go over the steps that might be taken with Spark to achieve our goal.

 * Clean the data by deleting unnecessary columns.

 * Clean the data by deleting rows that contain incomplete or duplicate data.

 * Rename the DataFrame columns to match those in the SQL tables.

 * Create new DataFrames with rows that will be inserted in the two SQL tables.

 * Load the DataFrames into the SQL database.

* In the next steps, use the `dropna()` and `dropDuplicates()` methods to drop rows containing junk data:

   ![Images/colab04.png](Images/colab04.png)

* Open pgAdmin, run the schema file, and explain that the table schemas are loaded into RDS. The actual rows of data from the DataFrames will be loaded into these tables on RDS.

  ```sql
  CREATE TABLE employee_personal_info (
    employee_id INTEGER PRIMARY KEY NOT NULL,
    email VARCHAR,
    gender VARCHAR,
    hire_date VARCHAR,
    dob VARCHAR
  );

  CREATE TABLE employee_password (
    employee_id INTEGER PRIMARY KEY NOT NULL,
    password VARCHAR
  );
  ```

* Examine the DataFrame schema to match the columns with those necessary in the SQL tables.

  ![Images/colab06.png](Images/colab06.png)

 * As discussed above, `DOB` and `Hire Date` columns are in the `timestamp` data type in the DataFrame and will become a `date` data type in SQL.

 * Students should replace `<insert password>` and `<insert aws endpoint>` with their account information.

* Explain that the columns that will be exported into SQL are renamed in lowercase letters. Also, following convention, spaces are replaced with underscores.

  ![Images/colab07.png](Images/colab07.png)

* Explain that a new DataFrame, called `employee_personal_info`, is created with the columns needed for its SQL counterpart.

  ![Images/colab08.png](Images/colab08.png)

* Explain that this cell sets the configuration for the Postgres database.


  ```python
  # Configuration for RDS instance
  mode="append"
  jdbc_url = "jdbc:postgresql://<insert endpoint>:5432/my_data_class_db"
  config = {"user":"root",
            "password": "<insert password>",
            "driver":"org.postgresql.Driver"}
  ```

 * The endpoint and password will need to be inserted here.

 * Since the schema for the SQL table `employee_personal_info` was already created in Postgres, the `mode` here is `append` rather than `overwrite`.

* Explain that this cell inserts the data from the DataFrame into a SQL table.

  ```python
  # Write DataFrame to table

  employee_personal_info.write.jdbc(url=jdbc_url, table='employee_personal_info', mode=mode, properties=config)
  ```

* Verify that the table has been populated in pgAdmin using a query:

  ![Images/etl07.png](Images/etl07.png)

* Repeat the above steps for the `employee_password` DataFrame and table.

 * First, select the columns.

    ```python
    employee_password = df1.select(["employee_id", "password"])
    employee_password.show(5)
    ```

 * Write to the database.

    ```python
    # Write DataFrame to table

    employee_password.write.jdbc(url=jdbc_url, table='employee_password', mode=mode, properties=config)
    ```

* A new DataFrame is created and loaded into RDS.

* Send out the [solution files](Activities/04-Stu_ETL_S3_Colab/Solved/) for students to refer to later.

* Answer any question before moving on to AWS cleanup.

</details>



- - -

### 6. AWS Cleanup

| Activity Time:       0:15 |  Elapsed Time:      1:55  |
|---------------------------|---------------------------|

<details>
 <summary><strong> 🎉 6.1 Everyone Do: AWS Cleanup (0:15)</summary></strong>

* **Important** Send out the [AWS Clean up guide](Activities/05-Evr_AWS_cleanup/AWS_cleanup.pdf) and [AWS Check billing guide](Activities/05-Evr_AWS_cleanup/AWS_check_billing.pdf) to students for future reference. Make sure students are able to follow along in class to manage their AWS cleanup at the end of class.

* Explain to students that everything we have done today will fall under the AWS Free Tier. However, as a precaution, we will delete everything we created. Let students know that they can recreate everything using the processes learned today. You can use slides 64-77 to accompany this activity.

* To delete the RDS database, follow these steps:

* Log in to the AWS management console and navigate to the **RDS** dashboard. Click **DB Instances**.

  ![DB instance](Images/db_instance.png)

* Select **DB Name** and click **Modify**.

  ![Modify DB](Images/modify_db.png)

* Scroll down to **Deletion protection** and uncheck the box next to **Enable deletion protection**. If the box is already unchecked, you can navigate back to the instance page and continue.

* If the box needs to be unchecked, click **Continue**, select **Apply immediately**, then **Modify DB Instance**.

  ![deletion protection](Images/delete_proc.png)

* Next, on the database dashboard, make sure the database is checked, and then click **Actions** followed by **Delete**.

  ![delete DB](Images/delete_db.png)

* **Important:** Uncheck **Create final snapshot?**, then check the acknowledgement box. Type **delete me** and click **Delete**. If you do not uncheck this box, your databases will create a backup that could accrue additional costs, so be sure not to skip over this step.

  ![final delete](Images/final_delete.png)

* This will take a few minutes to fully delete.

* To delete any S3 buckets, navigate to the S3 dashboard and follow these steps:

 * **Note:** This process will delete the whole bucket and all its contents. For the sake of time, this will be the process. Mention to students that individual files inside a bucket might be deleted as well.

 * Check the box next to the bucket you want to delete, then click **Empty**.

    ![empty bucket](Images/empty_bucket.png)

 * Enter **permanently delete** into the text box, and then click **Empty**.

 * Once the previous step is complete, click **Exit** exit on the next screen

 * With the bucket still selected, click **Delete**.

 * On the next screen, enter the bucket name in the input field and then click **Delete bucket**.

 * The bucket and all of its files are now deleted.

 * Sends out the [AWS Billing Check](Activities/05-Evr_AWS_cleanup/AWS_check_billing.pdf) that instructs students how to double-check their billing costs.

* Reconfirm with students that they were able to delete everything and that everyone has the [AWS Cleanup guide](Activities/05-Evr_AWS_cleanup/AWS_cleanup.pdf) and [AWS Check billing guide](Activities/05-Evr_AWS_cleanup/AWS_check_billing.pdf) before moving on to the end of class.

</details>



- - -

### 7. Ending Class

| Activity Time:       0:05 |  Elapsed Time:      2:00  |
|---------------------------|---------------------------|

<details>
 <summary><strong>📣  7.1 Instructor Do: Review </strong></summary>

* Before ending class, review the skills that were covered today and mention where in the module these skills are used.
 * Using AWS was covered in **Lesson 16.7.1**.
 * Creating an RDS instance was covered in **Lesson 16.7.2**
 * Connecting pgAdmin to an RDS instance was covered in **Lesson 16.7.3**.
 * CRUD functions were covered in **Lesson 16.7.4**.
 * AWS S3 was covered in **Lesson 16.8.2** and **Lesson 16.8.3**
 * PySpark ETL with AWS was covered in **Lesson 16.9.1**
 * AWS Cleanup and managing billing were covered in **Lesson 16.9.2** and **Lesson 16.9.3**

* Answer any questions the students may have.

</details>



- - - 

© 2021 Trilogy Education Services, LLC, a 2U, Inc. brand.  Confidential and Proprietary.  All Rights Reserved.
