# Overview

AutosRUs’ newest prototype, the MechaCar, is suffering from production troubles that are blocking the manufacturing team’s progress. AutosRUs’ upper management has called on the data analytics team to review the production data for insights that may help the manufacturing team.

In this challenge, you’ll help the data analytics team do the following:

Perform multiple linear regression analysis to identify which variables in the dataset predict the mpg of MechaCar prototypes
Collect summary statistics on the pounds per square inch (PSI) of the suspension coils from the manufacturing lots
Run t-tests to determine if the manufacturing lots are statistically different from the mean population
Design a statistical study to compare vehicle performance of the MechaCar vehicles against vehicles from other manufacturers. For each statistical analysis, you’ll write a summary interpretation of the findings.

# Delivarables

## Delivarable 1: Linear Regression to Predict MPG

MechaCar_mpg.csv dataset contains mpg test results for 50 prototype MechaCars, measuring the miles per gallon across multiple variables. R in RStudio was used to calculate and show the linear regression.

To deliver the findings the following steps were followed:

MechaCar_mpg.csv was imported and read into a DataFrame
RScript was written to show a linear regression model, performed on six variables
RScript was also written to show statistical summary of the linear regression model with the intended p-values
Written summary covering the three questions

MechaCar_DataFrame

![202325917-81588d58-5a3a-47b3-8bb6-e3c1dc96c37c](https://user-images.githubusercontent.com/109055148/213020225-72478476-36db-4822-bbe3-91cf729b5e20.png)

## Statistical Model

mpg = (6.267)vehicle_length + (0.0012)vehicle_weight + (0.0688)spoiler_angle + (3.546)ground_clearance + (-3.411)AWD + (-104.0)
![202329003-5b21c038-694b-4961-83f7-8ea8d639787e](https://user-images.githubusercontent.com/109055148/213020639-5f9192d5-9739-45a2-b7d8-0417a606c7ea.png)

## Statistical Summary

The vehicle length, and ground clearance are likely to provide non-random amounts of variance to the model. That is, the vehicle length and ground clearance have a significant impact on miles per gallon on the prototype. The vehicle weight, spoiler angle, and All Wheel Drive (AWD) have p-Values that show to have random amounts of variance with the dataset presented
P-Value: 5.35e-11, is much smaller than the assumed level of 0.05%. This indicates there is enough evidence to reject our null hypothesis, which indcates that the slope on this linear model is not zero.
The linear model has a r-squared value of 0.7149, approximately 71% of all mpg predictions will be determined by this model. The multiple regression model does predict mpg of MechaCar prototypes effectively.

# Deliverable 2: 

The Suspension_Coil.csv dataset shows results for multiple production lots. The wight capabilities of various suspension coils have been tested to determine if the manufacturing process is consistent across each of the production lots sampled.

Suspension coil’s PSI continuous variable across all manufacturing lots
PSI metrics for each lot: mean, median, variance, and standard deviation.
Technical Analysis
The summary statistics of all of the manufacturing lots. The mean is 1498.78 for this sample and the population mean was determined to be 1500.

![202792567-cf94f710-47fe-4ffe-9dbf-619f14b45a68](https://user-images.githubusercontent.com/109055148/213020803-1b2efe97-eb23-4e2f-ad5d-b2eda91b9293.png)

## Summary by Manufacturing Lot Number

The means of the lot numbers are similar to the population mean as well as the sample mean

![202792730-e3faaeb5-d38f-4b7d-a2b4-73652ba0e331](https://user-images.githubusercontent.com/109055148/213020888-bb5d3b62-0cb1-4829-be30-467d1b046c39.png)

The design specifications for the MechaCar suspension coils dictate that the variance of the suspension coils must not exceed 100 pounds per square inch. Does the current data meet this design specification for all manufacturing lots, in total, and each lot individually?

The variance for the total manufacturing lot is 62 < 100, which is within the expected design specifications of staying under 100 PSI. However, when reviewing the data by Lot number, Lot 3 is a large contributing factor to the variance being high. Lot 3 shows a variance of 170 > 100 and does not meet the design specifications. Lot 1 and Lot 2 have significantly lower variance, than 1 and 7 respectively.

# T-Tests on Suspension Coils
## T-test for all Lots
Manufacturing Lots: p-value = .6028, alpha = .05

.60 > .05, the total manufacturing lot is not statistically significant from the normal distribution, and normality can be assumed. While the mean falls within the 95% confidence interval.


![202795743-676e93a6-5827-469e-8b25-dcdbdc28063c](https://user-images.githubusercontent.com/109055148/213021071-86f7c8bc-4bf4-4377-96d5-c758efdbb331.png)

T-test for Lot 1

![202795929-a7df2692-1b35-40a8-96e7-5888b069c491](https://user-images.githubusercontent.com/109055148/213021097-b8e7ce8b-f7fa-4fc5-bd35-28e40d204d23.png)

## T-test for Lot 2

Lot 2: p-value = .6072, alpha = .05

.60 > .05, Lot 2 is not statistically significant from the normal distribution and normality can be assumed. While the mean falls within the 95% confidence interval.

![202796191-51e9c08b-6fe6-40ed-9fa7-a8fc0e12b3a5](https://user-images.githubusercontent.com/109055148/213021548-d64a938a-1af9-45c6-ba5a-ba204830fd83.png)

## T-test for Lot 3

Lot 3: p-value = .04168, alpha = .05

.04 < .05, which means it is statistically significant from the normal distribution and normality cannot be assumed. However, the mean falls within the 95% confidence interval.


![202796358-45f8e038-5416-4d85-9461-ead539b81a70](https://user-images.githubusercontent.com/109055148/213021643-4893b07b-633c-4aec-940e-5f5a2fffc15a.png)


Ooverall, Lots 1 & 2 show a normal distribution. There is not sufficient evidence to reject the null hypothesis, which shows the two means are statistically similar.

## Study Design: MechaCar vs Competition

When comparing MechaCar to its competitor’s some other metrics that may be of interest to consumer's, include cost, color of vehicle, city/highway fuel efficiency, horsepower, average cost of repair, and safety rating.

What metric or metrics are being tested?

The metrics to test should be horsepower, safety rating, and city/highway fuel efficiency, these could address some of the safety concerns consumers may have when buying a vehicle.
What is the null hypothesis or alternative hypothesis?

The null hypothesis is that the mean of the safety rating is zero. The alternative hypothesis is that the mean of the safety rating is not zero.
What statistical test would you use to test the hypothesis? And why?

A multiple linear regression statistical summary will show the variable impact of the safety ratings for MechaCar and competitors.
What data is needed to run the statistical test?

Random sample of n > 30 for MechaCar and each competitor would need to be collected, include the safety ratings, city/highway fuel efficiency, and horsepower, also, running the data through RStudio.
