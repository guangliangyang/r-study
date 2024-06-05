
## Introduction
 
  
Airbnb, as a prominent product of the sharing economy, has indeed seen rapid growth in recent years, providing a unique alternative to traditional hotel accommodations with a wide range of short-term and long-term lodging options. Various studies have delved into different aspects of Airbnb, particularly focusing on the factors that influence customer satisfaction and ratings [@customer1]. One key area of research has been the impact of factors such as listing functionality, host attributes, customer reviews, and market conditions on guest satisfaction. These studies aim to understand how these elements collectively shape the overall experience of guests, ultimately influencing their review scores and the likelihood of them returning [@customer2]. For example, the quality of service provided by hosts, the amenities offered, and the location of the accommodation all play crucial roles in determining guest satisfaction levels [@customer3]. Moreover, research has also highlighted the significance of rental policies, listing reputation, and location in influencing guest satisfaction levels. Factors such as the clarity of rental policies, the reputation of the listing, and the convenience of the location can greatly impact how satisfied guests are with their overall experience [@customer4]. By examining these various factors that contribute to customer satisfaction in the context of Airbnb, researchers aim to provide valuable insights for hosts and practitioners to enhance the overall guest experience and increase customer satisfaction levels [@customer1].

In this project, we aim to extend this body of research by focusing on the factors influencing property ratings and guest satisfaction on Airbnb, specifically for properties listed as "Apartments" We will explore the relationship between high ratings (scores greater than or equal to 95) and various predictors, including price, host tenure, number of reviews, regional average price, number of bedrooms, number of bathrooms, host response rate, and room type. By building suitable models, we seek to uncover the determinants of high ratings and provide actionable insights for property owners. Additionally, we will analyze how these factors can be adjusted to optimize guest satisfaction and improve overall ratings, thereby enhancing the competitive edge of Airbnb listings.

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
Can property ratings be predicted using price, regional average price, number of bedrooms , number of accommodates ,room types, and number of bathrooms ? 

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
Can high ratings (scores greater than or equal to 95) be predicted using price, host tenure (measured by "host_since_year" ), number of reviews, regional average price, and host response rate?

**1. Variables Considered:**

* **Price:** The nightly rental price of the property.
* **Host Since Year:** The year when the host joined Airbnb, indicating their tenure in the platform. 
* **Number of Reviews:** The total number of reviews received by the property.
* **Regional Average Price:** The average price in the region where the property is located, providing context for pricing.
* **Host Response Rate:** The rate at which the host responds to inquiries, reflecting host engagement and responsiveness.

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


 ## Conclusion
 

Our analysis provides several key insights into the factors influencing home ratings and guest satisfaction on Airbnb. These findings have practical implications for hosts who want to improve their listings and boost their ratings. In addition, I gained a deeper understanding of statistical analysis using R, which is valuable for future research and practical applications.

## Significance

This study highlights the significant impact of pricing strategy, room features, and host responsiveness on guest satisfaction. Hosts can use these insights to make strategic adjustments:

1. **Adjusting Prices:** Setting competitive and appropriate prices that reflect the quality of the listing can help meet or exceed guest expectations, thereby improving satisfaction.
2. **Enhancing Listing Features:** Adding more bathrooms and optimizing the number of nights can more effectively meet guests' needs, leading to better reviews.
3. **Improving Host Responsiveness:** Maintaining a high response rate can enhance the guest experience and promote positive reviews and higher ratings.
4. **Importance of Public Opinion:** The greater the number of reviews, the lower the likelihood of a positive review. Hosts need to pay more attention to public opinion.

By focusing on these areas, hosts can attract more bookings and receive better overall ratings, thereby improving their market presence and attractiveness.

## Limitations

While our analysis provides valuable insights, there are still some limitations to consider. Objective limitations, such as excluding variables related to location (e.g., latitude, longitude, neighborhood), are necessary because analyzing them requires more detailed information about transportation, local facilities, population density, and urban layout. Complexity is another factor; this experiment focuses primarily on learning statistical methods using R and is not intended to be a comprehensive analysis, but rather an attempt to explore the impact of some common variables on property ratings. In addition, several columns in the dataset are not used in our current analysis. These unused variables may contain valuable information that can enhance the predictive power of our model. Acknowledging these limitations is critical for interpreting results and considering areas for improvement.

## Challenges Encountered

In this study, we faced several challenges. Ensuring the accuracy and completeness of the dataset was a challenge, with missing values and inconsistent data entry requiring extensive preprocessing efforts. Selecting the most relevant variables from a large dataset is complex and requires careful consideration of each variable's potential impact on the analysis. Ensuring that the data meets the assumptions required for linear and logistic regression models is a challenge, especially in terms of normality and homoscedasticity of residuals. In Research Questions 2 and 3, we used different variables designed to predict high ratings, but still did not obtain accurate predictions. Specifically, the logistic regression models in Research Questions  2 and 3 showed that while higher price and host response rate were significant predictors of high ratings, the overall accuracy and predictive power of these models were limited.

## Future Work Opportunities

Future research can build on our findings to better understand the factors that drive guest satisfaction. Including more variables such as  “latitude” and “longitude” and then incorporating specific city maps, transportation, and business amenities can improve the accuracy and explanatory power of the model. Employing more sophisticated methods, such as machine learning, can better capture the complex relationships and interactions between variables. Studying changes over time can reveal how continuous improvements and price adjustments to properties affect guest satisfaction and ratings. Analyzing qualitative feedback from guest reviews can reveal additional factors that contribute to high ratings, providing more nuanced insights. Exploring the potential of unused columns can provide additional predictive power and provide more comprehensive insights into the dynamics of guest satisfaction. By exploring these opportunities, future research can enhance our understanding of guest preferences, help hosts better meet their needs, and ultimately improve ratings and succeed in the competitive Airbnb market.



