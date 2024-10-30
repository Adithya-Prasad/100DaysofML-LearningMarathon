# Day 3: Statistics Fundamentals — Mean, Median, Mode, Variance, Standard Deviation

Statistics is a core pillar of machine learning. It allows us to explore, summarize, and interpret data to find patterns and relationships. Today, we’ll cover some of the fundamental statistical concepts — mean, median, mode, variance, and standard deviation. These metrics help us describe a dataset’s shape, spread, and central tendency, providing crucial insights even before any modeling begins.

![Designer (3)](https://github.com/user-attachments/assets/80760409-4abe-415a-9e4c-c953edf76763)

If you are interested in taking your career in Data Science, then developing your interest in mathematics (especially statistics!) helps you a lot.

Try to understand how equations/formulas are created. Try finding the logical approach or reason behind:

**Why we are using this equation?**

**What is the relationship between the variables in this equation?**

**What is the result we are getting from this equation? and, how it will be useful for our use case?**

For ex: Watch this video by [DATAtab](https://www.youtube.com/watch?v=jx8a_jdlxAQ) to understand what variance means.

*Remembering every formula is difficult, but once you understand the concept, it will be stored in your memory permanently.*

## Why Statistics Matter in Machine Learning

When working with data, understanding its basic structure is essential. Statistical metrics offer insights into how data points are distributed, which helps identify potential outliers, assess variability, and understand the overall data trend. These metrics make it easier to select the right algorithms, optimize model performance, and communicate findings clearly.

## Central Tendency
*The tendency for the values of a random variable to cluster round its mean, mode, or median. — (Oxford definition)*

Central tendency simply means a single value that is trying to describe your set of data. It tries to refer to the center of the data distribution.

mean, median, and mode are normally called measures of central tendency which are often used in statistics.

![sketchplanations-measures-of-central-tendency-mean-median-mode](https://github.com/user-attachments/assets/353859c0-2829-4b4d-a8f6-3dc13eb24ed7)

Sourced from [Sketchplanation](https://sketchplanations.com/measures-of-central-tendency-mean-median-mode)

### 1. Mean
The mean (or average) is the sum of all values in a dataset divided by the number of values. It’s one of the most commonly used statistics and provides a simple representation of the dataset’s central tendency.

Formula:

![image](https://github.com/user-attachments/assets/e2a49e99-cbc8-4c32-b9ac-274688c9faf7)

For example, if we have daily sales data for a week: 100, 150, 200, 130, 180, 160, and 120, the mean would represent the “average sales” over the week.

### 2. Median
The median is the middle value in a dataset when the values are sorted in ascending or descending order. If there’s an odd number of values, the median is the middle one. For an even number of values, it’s the average of the two central values. Unlike the mean, the median isn’t affected by extremely high or low values(outliers), making it a useful measure for skewed datasets.

*[Skewed dataset](https://builtin.com/data-science/skewed-data#:~:text=Skewed%20data%20is%20data%20that,to%20the%20left%20or%20right.) is a collection of data with an asymmetrical distribution, where the values are not spread evenly across the range.*

Example:

For data [10, 20, 30, 40, 50], the median is 30.
For data [10, 20, 30, 40], the median is (20 + 30)/2 = 25.

### 3. Mode
The mode is the value that appears most frequently in a dataset. Some datasets may have no mode if all values are unique, while others can be multimodal if they have more than one mode.

Example:

For data [10, 15, 15, 20, 25], the mode is 15 (since it appears most often).
For data [5, 10, 10, 15, 15, 20], there are two modes: 10 and 15.

### 4. Variance
Variance measures how far each value in the dataset is from the mean. A higher variance indicates that data points are more spread out, while a lower variance means they’re closer to the mean. In machine learning, variance helps us understand data variability and distribution shape.

![image](https://github.com/user-attachments/assets/82af4de9-5cde-45c7-bbf3-be8638d4eef2)

For instance, knowing variance can help determine if a dataset is consistently close to its average value or if it’s dispersed across a wide range.

### 5. Standard Deviation
Standard deviation is the square root of variance and provides a measure of spread or dispersion in the same unit as the original data. Like variance, it helps indicate how concentrated or spread out values are relative to the mean.

Formula:

![image](https://github.com/user-attachments/assets/36d2a10b-ed98-464d-8625-90c0dafad34c)

## Calculating Test Scores in a Classroom
Imagine a classroom where the teacher, Mrs. Rao, has given a math test to her students. She wants to understand how the class performed overall, how consistent the scores were, and if there were any standout scores. To do this, she calculates the mean, median, mode, variance, and standard deviation of the scores.

With this information:

* She uses the **mean** to assess the average performance.
* She calculates the **median** to see the middle score, which helps if any students scored exceptionally high or low.
* The **mode** helps her identify the most common score, perhaps reflecting a grade level many students reached.
* Finally, the **variance** and **standard deviation** tell her if most students scored around the same range or if there were significant differences in performance.

Using these insights, Mrs. Rao can understand the overall class performance and where students might need additional help or practice.

## Calculating Basic Statistics in Python
Let’s look at a practical example using Python to calculate mean, median, mode, variance, and standard deviation for a sample dataset of student scores.

```
import numpy as np
from scipy import stats

# Test scores of students
scores = [75, 85, 90, 95, 85, 80, 78, 85, 92, 88]

# Mean
mean_score = np.mean(scores)
print("Mean:", mean_score)

# Median
median_score = np.median(scores)
print("Median:", median_score)

# Mode
mode_score = stats.mode(scores)
print("Mode:", mode_score.mode[0])

# Variance
variance_score = np.var(scores)
print("Variance:", variance_score)

# Standard Deviation
std_deviation_score = np.std(scores)
print("Standard Deviation:", std_deviation_score)
```

### Explanation of the Code
**Mean**: We use np.mean() from the NumPy library to calculate the average score.

**Median**: np.median() calculates the middle value of the sorted dataset.

**Mode**: stats.mode() from SciPy returns the most frequent value in the dataset.

**Variance**: np.var() measures the spread of scores from the mean.

**Standard Deviation**: np.std() provides the average distance of each score from the mean, giving a sense of score variability.

### Output
With the code above, you’ll get output like:

```
Mean: 85.3
Median: 85.0
Mode: 85
Variance: 37.81
Standard Deviation: 6.15
```
These results indicate that the average score is around 85, with most students scoring close to this value (as reflected by the low standard deviation). The mode shows that 85 was the most common score among students.

## Wrapping Up

Basic statistics are the stepping stones to understanding any dataset. Mean, median, and mode help us identify central trends, while variance and standard deviation give insight into the spread and consistency of values. Just as Mrs. Rao used these metrics to understand her students’ performance, you’ll use them to interpret and prepare data for machine learning projects.

With a solid grasp of these fundamental metrics, you’ll be ready to dive deeper into more complex analysis and modeling with confidence.

See you on the next topic!
