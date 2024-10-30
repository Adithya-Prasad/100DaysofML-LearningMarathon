# Day 2: Understanding Data in ML — Intro to Datasets, Data Structures, and Data Cleaning

*In the world of machine learning, data is the foundation. Think of it as the fuel that powers the engine of any ML model. Without good data, even the most advanced algorithms will struggle to produce meaningful results. Today, we’ll explore datasets, data structures, and data cleaning — the essentials of preparing data for ML projects.*

![Day2 Cover](https://github.com/user-attachments/assets/74c8c932-a899-4f6b-9e66-b3c773828fd4)

## Why is Data Important in Machine Learning?

Data is what enables machines to recognize patterns, make predictions, and improve over time. The type, structure, and quality of data directly affect how well an ML model performs. To build a powerful machine learning model, we first need to understand and prepare our data carefully.

Imagine trying to solve a complex puzzle, but with pieces that are incomplete or damaged. That’s similar to training an ML model on messy or unstructured data. The goal of data preparation is to ensure that our data is clean, structured, and ready for learning.

### 1. Understanding Datasets

A dataset is a collection of data points (often stored in a table format) used to train, validate, or test a machine learning model. **Each row in a dataset represents a unique instance or observation, while each column holds a specific feature or attribute of that instance.**

#### Example of a Dataset

Consider a simple dataset about customers for a retail store. Each row could represent a customer, and each column might include details like Age, Gender, Income, and Purchase History.

![Screenshot 2024-10-29 104720](https://github.com/user-attachments/assets/1d05f8e3-3570-4a7b-a688-5e189465d3c8)

Each column provides a specific feature about the customers, and this information could be used to **predict**, let's say, which products customers are likely to buy in the future.

### 2. Data Structures in Machine Learning

Data comes in many forms, and the structure of data can vary widely based on the task:

![Screenshot 2024-10-29 110316](https://github.com/user-attachments/assets/6f494b8b-db88-4fc5-b03b-804b98aff9a9)

 - **Tabular Data**: Structured data in rows and columns (like spreadsheets) is the most common format. This data is easy to work with in ML because each column can be treated as a feature.
 - **Time Series Data**: Data collected at regular time intervals (such as stock prices or weather data). Each time step is a data point, which helps in making predictions based on past trends.
 - **Text Data**: Includes documents, messages, and other written forms. Text needs to be transformed into numerical representations (like word counts or embeddings) to be used in ML.
 - **Image Data**: Data in the form of pictures or videos. Image data requires specialized techniques for processing and understanding, such as convolutional neural networks.

### 3. Data Cleaning

Data cleaning is the process of preparing raw data so it’s consistent and free of errors. Messy data can result from a variety of issues — missing values, outliers, duplicates, and even irrelevant information. Cleaning the data involves handling these problems so our model can learn effectively.

#### Common Data Cleaning Steps

 - **Removing Duplicates**: Duplicate rows can skew results by overemphasizing specific data points, so they’re typically removed.
 - **Handling Missing Values**: Missing values can be filled (imputed) with the mean, median, or a similar metric, or rows with missing data can be removed altogether.
 - **Outlier Detection**: Outliers are unusual values that stand far away from the majority of data points. While some outliers are useful, others can disrupt learning. These can be capped or removed.
 - **Converting Data Types**: Inconsistent formats, such as dates stored as text, need to be converted into usable types.

Let’s illustrate these concepts with a short example.
#### Preparing Data for a School Admissions Model

Imagine a school principal, Mr. Sharma, who wants to predict which students are likely to excel in their first year based on their previous academic records. He collects data on student grades, extracurricular activities, and attendance, but finds that the data is messy. Some records are incomplete, others are duplicated, and a few students have unusually high or low grades.

Mr. Sharma understands that he needs to clean and organize the data to get accurate predictions. So, he sits down to remove duplicates, handle missing values, and normalize grades. With clean data, Mr. Sharma feels confident that his model will identify the students who might need extra support to excel.

#### Code Example: Data Cleaning in Python

Below is a basic example of data cleaning in **Python** using pandas, a powerful data manipulation library.

```
import pandas as pd

# Sample dataset
data = {
    'StudentID': [1, 2, 3, 3, 4],
    'Grade': [85, None, 95, 95, 78],
    'Attendance': [95, 85, 88, 88, None],
    'Extracurricular': ['Football', 'Debate', None, 'Drama', 'Debate']
}

df = pd.DataFrame(data)

# original data
print("Original Data:")
print(df)

# Remove duplicates
df = df.drop_duplicates()

# Handle missing values
df['Grade'] = df['Grade'].fillna(df['Grade'].mean())  # Replace with mean grade
df['Attendance'] = df['Attendance'].fillna(df['Attendance'].median())  # Replace with median attendance
df['Extracurricular'] = df['Extracurricular'].fillna('No Activity')  # Replace None with 'No Activity'

# cleaned data
print("\nCleaned Data:")
print(df)
```

#### Output:
The cleaned data will look like this:
```
Original Data:
   StudentID  Grade  Attendance Extracurricular
0          1   85.0       95.0        Football
1          2    NaN       85.0          Debate
2          3   95.0       88.0             NaN
3          3   95.0       88.0           Drama
4          4   78.0        NaN          Debate

Cleaned Data:
   StudentID  Grade  Attendance Extracurricular
0          1   85.0       95.0        Football
1          2   86.0       85.0          Debate
2          3   95.0       88.0       No Activity
4          4   78.0       88.0          Debate
```

#### Explanation of the Code

 - **Removing Duplicates**: The drop_duplicates() function removes duplicate rows, ensuring each student is only represented once.
 - **Handling Missing Values**: We use different methods for different columns:
     - **Grade** is filled with the **mean**.
     - **Attendance** is filled with the **median**.
     - **Extracurricular** is filled with “No Activity” to replace missing values with a meaningful default.

We will be doing end-to-end **Exploratory Data Analysis (EDA:a systematic process for analyzing data to identify patterns, relationships, and anomalies; treating the data and processing the data as per the requirement)** & **Feature Engineering(a data preparation step that transforms raw data into a more effective set of inputs for ML models)** in the coming days. The above is just a basic understanding.

## Wrapping Up

Data is the lifeblood of machine learning, and understanding it is crucial for building accurate models. By learning how to handle datasets, data structures, and data cleaning techniques, you’re setting up a strong foundation for the exciting tasks ahead. Clean, organized data will always yield better predictions and more reliable results in any ML project.

As you move forward, remember Mr. Sharma’s journey with his student data. In the same way, organizing and cleaning your data can make all the difference in creating impactful machine learning solutions.

Some useful resources:

[Altexsoft: How data is prepared for Machine Learning](https://www.youtube.com/watch?v=P8ERBy91Y90)

[Bhupen: Making sense of DATA for ML/DL modeling](https://www.youtube.com/watch?v=ZiK-yJWvhbw)

*Happy Cleaning!*
