Dataset Size: 10841 Records

PROBLEM STATEMENT-

1. Find out top 10 reviews given to the apps
2. Top 10 app installs and distribution of type (free/paid)
3. Category wise distribution of installed apps
4. Top paid apps

Data View- 

<img width="1029" alt="Screenshot 2024-06-28 at 6 38 35 PM" src="https://github.com/MannatKaurBhatia/Google-Play-Store---PySpark-Project/assets/72853447/bbb127ac-8090-4e7c-909f-d4908c04e673">

Steps Followed to build this project:

1. Understanding the Task/Problem Statement and Finding the Dataset:
   
a. Objective: Clearly define the task or problem statement. Understand the requirements and objectives of the project.
b. Dataset Search: Identify and locate a suitable dataset that can help you solve the problem. This could involve searching for datasets on platforms like Kaggle, UCI Machine Learning Repository, or other open data sources.

2. Downloading the Dataset and Exploring It

a. Download: Download the dataset to your local machine or a cloud environment where you will perform the analysis.
b. Initial Exploration: Open the dataset in a tool like Excel, Google Sheets, or a text editor to get a preliminary understanding of its structure and contents. Note key columns and data types.

3. Installing PySpark and Importing PySpark into Jupyter Notebook

a. Installation: Install PySpark if it’s not already installed:  
!pip install pyspark 
from pyspark.sql import SparkSession
spark = SparkSession.builder.appName("GooglePlayStore-Project").getOrCreate()

4. Loading the Dataset

a. Read Dataset: Load the dataset into a Spark DataFrame:
  df = spark.read.csv("path/to/your/dataset.csv", header=True, inferSchema=True)

5. Viewing the Count of Records and Understanding the Schema
   
a. Check the number of records: df.count()  
b. Print the schema of the DataFrame to understand the structure: df.printSchema()


6. Data Cleaning

a. Remove Irrelevant Columns: Drop columns that are not needed:
b. Handle NaN Values: Remove or impute NaN values:
c. Data Type Conversion**: Convert columns to appropriate data types. For example, converting a mixed-type "Installs" column to an integer:

  from pyspark.sql.functions import regexp_replace, col
  df = df.withColumn("Installs", regexp_replace(col("Installs"), "[^0-9]", "").cast("int"))

7. Installing SQL for Use with PySpark

a. To use SQL within Jupyter Notebook: pip install ipython-sql
b. Load SQL extension in your notebook: %load_ext sql

8. Solving the Problem Tasks by Writing SQL Commands
