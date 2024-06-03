
## Introduction
 
Airbnb, as a prominent product of the sharing economy, has indeed seen rapid growth in recent years, providing a unique alternative to traditional hotel accommodations with a wide range of short-term and long-term lodging options. Various studies have delved into different aspects of Airbnb, particularly focusing on the factors that influence customer satisfaction and ratings [@customer1]. One key area of research has been the impact of factors such as listing functionality, host attributes, customer reviews, and market conditions on guest satisfaction. These studies aim to understand how these elements collectively shape the overall experience of guests, ultimately influencing their review scores and the likelihood of them returning [@customer2]. For example, the quality of service provided by hosts, the amenities offered, and the location of the accommodation all play crucial roles in determining guest satisfaction levels [@customer3]. Moreover, research has also highlighted the significance of rental policies, listing reputation, and location in influencing guest satisfaction levels. Factors such as the clarity of rental policies, the reputation of the listing, and the convenience of the location can greatly impact how satisfied guests are with their overall experience [@customer4]. By examining these various factors that contribute to customer satisfaction in the context of Airbnb, researchers aim to provide valuable insights for hosts and practitioners to enhance the overall guest experience and increase customer satisfaction levels [@customer1].

In this project, we aim to extend this body of research by focusing on the factors influencing property ratings and guest satisfaction on Airbnb. Specifically, we will explore the relationship between high ratings  (scores greater than or equal to 95) and various predictors, including price, regional average price, number of bedrooms, number of bathrooms, host response rate, and room type. By building suitable models, we seek to uncover the determinants of high ratings and provide actionable insights for property owners. Additionally, we will analyze how these factors can be adjusted to optimize guest satisfaction and improve overall ratings, thereby enhancing the competitive edge of Airbnb listings.

## Dataset Description

### Source
The dataset to be analyzed is collected from https://data.world/cannata/gaairbnb and is named "AirBNB.csv". 

### File Type
Dataset file type: CSV


### Type of Data Cleaning Expected
 
The variables selected for analysis are `price`, `accommodates`, `bathrooms`, `bedrooms`, `room_type`, `host_response_rate`, and `review_scores_rating`.

#### Data Wrangling Steps


We propose the following data wrangling steps:

1. **Filtering Observations** :
   * Filter out observations related to property_type "apartment".
   * Select the necessary variables for analysis.
2. **Handling Missing Values** :
   * Identify and handle missing values appropriately. This may include removing rows with significant missing data or imputing missing values using appropriate methods.
3. **Data Type Conversion** :
   * Ensure all columns are of the correct data type. Convert columns to appropriate types (e.g., numeric, factor, date) as necessary.
4. **Removing Duplicates** :
   * Check for and remove any duplicate rows to ensure each observation is unique. 
5. **Outlier Detection and Treatment** :
   * Identify and treat outliers that may skew the analysis. This can involve removing extreme values or transforming them.
6. **Creating New Features** :
   * Create new features that may be useful for analysis, such as calculating the age of the listing from the `host_since_year` variable. 
7. **Encoding Categorical Variables** :
   * Encode categorical variables (e.g., room_type) using techniques such as one-hot encoding or label encoding to make them suitable for analysis and modeling.

These steps will help ensure that the dataset is clean, consistent, and ready for further analysis and modeling.

\newpage

## Three proposed research questions
 
### Research question 1

Do properties with prices at different levels relative to the regional average price have significantly different ratings?



**1. Variables Considered:**

* **Price:** The nightly rental price of the property.
* **Region Average Price:** The average price in the region where the property is located.
* **Review Scores Rating:** The overall rating given by guests.

**2. Type of Analysis:**

* **Grouping:** Properties are divided into groups based on their price relative to the regional average price.
* **Descriptive Statistics:** Mean and standard deviation of review scores for each price group.
* **ANOVA:** To test for significant differences in review scores across the price groups.
* **T-Test:** To compare the review scores between two specific groups (below_avg and above_avg).
* **Visualization:** Box plot to visualize the distribution of review scores across price groups.

**3. Libraries and Required R Functions:**

* **dplyr:** For data manipulation and grouping.
* **ggplot2:** For creating visualizations.
* **stats:** For performing ANOVA and t-tests.
* **knitr:** For creating tables in the report.


### Research question 2
Can property ratings be predicted using price, regional average price, number of bedrooms , number of accommodates , and number of bathrooms ? Additionally, are the differences in ratings significant across different room types?

**1. Variables Considered:**

* **Price:** The nightly rental price of the property.
* **Region Average Price:** The average price in the region where the property is located.
* **Bedrooms:** The number of bedrooms in the property.
* **Accommodates:** The number of guests the property can accommodate.
* **Bathrooms:** The number of bathrooms in the property.
* **Room Type:** The type of room (e.g., entire home/apartment, private room, shared room).
* **Review Scores Rating:** The overall rating given by guests.

**2. Type of Analysis:**

* **Linear Regression:** To model the relationship between the review scores rating and the predictor variables.
* **Residual Analysis:** To assess the fit of the linear regression model by examining the residuals.
* **QQ Plot:** To check the normality of residuals, which is an assumption of linear regression.

**3. Libraries and Required R Functions:**

* **dplyr:** For data manipulation.
* **ggplot2:** For creating visualizations.
* **car:** For generating QQ plots.
* **stats:** For building and analyzing the linear regression model.
* **knitr:** For creating tables in the report.


### Research question 3
Can high ratings  (scores greater than or equal to 95) be predicted using price, regional average price, number of bedrooms, number of bathrooms, host response rate , and room type?

**1. Variables Considered:**

* **Price:** The nightly rental price of the property.
* **Region Average Price:** The average price in the region where the property is located.
* **Bedrooms:** The number of bedrooms in the property.
* **Bathrooms:** The number of bathrooms in the property.
* **Host Response Rate:** The rate at which the host responds to inquiries.
* **Room Type:** The type of room (e.g., entire home/apartment, private room, shared room).
* **High Rating (Binary):** Whether the property received a rating of 95 or higher (1 for high rating, 0 otherwise).

**2. Type of Analysis:**

* **Logistic Regression:** To model the relationship between the binary high rating variable and the predictor variables.
* **Confusion Matrix:** To evaluate the accuracy, sensitivity, and specificity of the logistic regression model.
* **ROC Curve and AUC:** To assess the model's ability to distinguish between high and low ratings.

**3. Libraries and Required R Functions:**

* **dplyr:** For data manipulation.
* **ggplot2:** For creating visualizations.
* **caret:** For generating confusion matrix and performance metrics.
* **ROCR:** For generating ROC curve and calculating AUC.
* **stats:** For building and analyzing the logistic regression model.
* **knitr:** For creating tables in the report.
