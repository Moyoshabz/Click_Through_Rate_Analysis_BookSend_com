# Click Through Rate Analysis for BookSend.com



# Introduction

In the current era of digital communication, email marketing campaigns are essential for keeping audiences engaged and driving business growth. To achieve this, it's crucial to understand the click-through rates (CTRs) of these campaigns, which help optimize future emails and inform advertising rates.  

This report focuses on modeling the CTR for Booksend.com using historic data for 50,000 emails, performing exploratory data analysis (EDA), identifying important features and trends, and evaluating using efficient predictive models to optimize performance and proffer recommendations for the business.



# Data Description 

## Understanding the Dataset
Dataset Source: Case2_final_adTech_data.csv
Data types: Char, Num, Int
Observation:50,000
Variable: 12

### Data Variables Explained
**Email_ID**: Unique identifier for each email.

**Subject_Marketability_score:** Expected attractiveness of the email subject, indicating potential click-through rate (CTR).

**Customer_Location**: State of the recipient identified through IP address.

**Total_Past_Communications:** Total number of past emails received by the recipient.

**Word_Count**: Length of email text, carefully designed to attract clicks without overwhelming readers.

**Total_Links:** Number of offers or links in the email.

**Total_Images:** Number of images used in the email.

**Signup_Site:** Category or email list to which the recipient is subscribed.

**Genre:** Main genre of the email offering, encoded with factors.

**Sent_Hour:** Timestamp indicating the hour when the email was sent.

**Browser**: Browser used by the recipient to open the email.

**Y_click:** Dependent variable indicating whether the email was opened and clicked (1) or not clicked (0).



## Partitioning Utilized a 70-20-10 split
70% of the data is allocated to the training set, 20% of the data is allocated to validation set and, 10% allocated to test the set .

## Modeling Techniques
**Decision Tree**

**Random Forest**

## Exploratory Data Analysis (EDA)

An Overview of the dataset

![iamge_1](./images/image2.png)


**0 – Not clicked**

**1 - Clicked**

![iamge_1](./images/image3.png)


## Click and not click distribution

![iamge_1](./images/image4.png)


## Click through rate per browser

![iamge_1](./images/image5.png)

## Relationship between Genre and Click-through rate

![iamge_1](./images/image6.png)


**Observation:** 

Irrespective of the genre, the non click rates are uniform across all genre

## Click through rate and relationship with images 

![iamge_1](./images/image7.png)

**Observation:** 

There is 50% chances of clicks with more images


# EDA - Data preparation for Modelling

After observing the data using basic EDA, it was observed that some columns within the dataset contained missing values(**NA’s**)

Below are the columns:

**Subject_Marketability_score**

**Total_Past_Communication**

**Word_Count**

**Total_links**

**Total_Images**

In other to avoid skewness in the training and prediction process and bias or incomplete decision, the use of imputation techniques would be used to fill the missing values

## Imputation techniques adopted 

**Mean or median imputation for the numeric columns**

**Assign a separate category for the categorical variable column**

## Before Imputation

**Observation:**  
Each column contains NA's

![iamge_1](./images/image8.png)


## After Imputation
**Observation: ** After mean and median imputation they are no instances of missing rows(NA’s) within the dataset


![iamge_1](./images/image9.png)


# Feature Engineering

## Feature Selection: Subject_Marketability_score and Word_count

**Subject_Marketability_score:** This feature was chosen based on its expected correlation with the click-through rate (CTR). 
Higher scores indicate a higher expected CTR, making it a valuable predictor.

![iamge_1](./images/image10.png)


**Observations:**

The visualization seems to tell a different story on the relationship between subject marketability score and the click through rates in the data set


**Word_Count:** The length of the email text was selected as it is believed that an optimal word count can maximize reader engagement. 
Too little text may not effectively sell to readers, while too much can be overwhelming.

![iamge_1](./images/image11.png)

**Observation:**

The maximum word_count that could influence the click-through rate is **between 300-320**


# Model Selection and Evaluation

We trained decision trees and random forests using 50,000 historical email data. Our evaluation of the models was based on their prediction performance, specifically accuracy, precision, recall, and other relevant metrics. These metrics provide insights into the models' ability to predict click-through rates, guide decision-making for improving future emails, and inform the rate to charge advertisers.


## Decision Tree : Confusion Matrix

Training Prediction - Actual vs Prediction

Accuracy: 93.9%























