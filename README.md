# MechaCar_Statistical_Analysis

## Resources

* Data Source: [MechaCar - MPG](https://github.com/doliver231/MechaCar_Statistical_Analysis/blob/main/MechaCar_mpg.csv), [MechaCar - Suspension Coils](https://github.com/doliver231/MechaCar_Statistical_Analysis/blob/main/Suspension_Coil.csv)
* R Script: [MechaCar R-Script](https://github.com/doliver231/MechaCar_Statistical_Analysis/blob/main/MechaCarChallenge.R)
* Software/Languages: R Programming, R Studio 2022.12.0, Tidyverse Library

## Linear Regression to Predict MPG

![Linear Model](https://github.com/doliver231/MechaCar_Statistical_Analysis/blob/main/Images/Deliverable1_ln().png)
![Summary of LM](https://github.com/doliver231/MechaCar_Statistical_Analysis/blob/main/Images/Deliverable1_summary.png)

* Which variables/coefficients provided a non-random amount of variance to the mpg values in the dataset?

According to the ```Pr(>|t|)``` values, 'ground_clearance' and 'vehicle_length' show the least probability that they will contribute to random amounts of variance to the linear model. In other words, they have significant impact on 'mpg'. Variables 'vehicle_weight', 'spoiler_angle', and 'AWD' show they are statistically likely that they will provide random amount of variance to the linear model.

* Is the slope of the linear model considered to be zero? Why or why not?

Our p-value for our multiple linear regression model = 5.35e-11. This value is less than our significance level of 0.05. This means we reject our null hypothesis that the slope is zero. Therefore, the slope of our linear model is NOT zero. The coefficients of each variable are also all non-zero.

* Does this linear model predict mpg of MechaCar prototypes effectively? Why or why not?

Our R-squared value is 71%, which means roughly ~71% of the time the model will predict mpg values correctly. There are probably other factors that were not captured in the dataset that contribute to the mpg variability of the MechaCar prototypes.

## Summary Statistics on Suspension Coils

![Total coils](https://github.com/doliver231/MechaCar_Statistical_Analysis/blob/main/Images/Deliverable2_total.png)
![Lots summary](https://github.com/doliver231/MechaCar_Statistical_Analysis/blob/main/Images/Deliverable2_lotSummary.png)

* The design specifications for the MechaCar suspension coils dictate that the variance of the suspension coils must not exceed 100 pounds per square inch. Does the current manufacturing data meet this design specification for all manufacturing lots in total and each lot individually? Why or why not?

The variance for the total manufacturing lots is 62.2 PSI, which is within the expected design specifications of staying under 100 PSI. However, when reviewing the data by Lot number, Lot 3 is a large contributing factor to the variance being high, with a variance of 170.3 PSI, so it does not meet the design specifications. Lot 1 and Lot 2 have significantly lower variance, 0.98 PSI and 7.5 PSI respectively.

## T-Tests on Suspension Coils

![Total](https://github.com/doliver231/MechaCar_Statistical_Analysis/blob/main/Images/Deliverable3_allLots.png)

Our t-test resulted with a p-value = 0.06028, which is greater than our significance level of 0.05. So we can conclude that we do NOT have sufficient evidence to reject the null hypothesis, and the sample and population means are statistically similar.

![Lot1](https://github.com/doliver231/MechaCar_Statistical_Analysis/blob/main/Images/Deliverable3_Lot1.png)

We performed the analysis on individual group, Lot 1. Our t-test resulted with a p-value = 1.0, which is greater than our significance level of 0.05. So we can conclude that we do NOT have sufficient evidence to reject the null hypothesis, and the sample and population means are statistically similar.

![Lot2](https://github.com/doliver231/MechaCar_Statistical_Analysis/blob/main/Images/Deliverable3_Lot2.png)

We performed the analysis on individual group, Lot 2. Our t-test resulted with a p-value = 0.6072, which is greater than our significance level of 0.05. So we can conclude that we do NOT have sufficient evidence to reject the null hypothesis, and the sample and population means are statistically similar.

![Lot3](https://github.com/doliver231/MechaCar_Statistical_Analysis/blob/main/Images/Deliverable3_Lot3.png)

We performed the analysis on individual group, Lot 3. Our t-test resulted with a p-value = 0.04168, which is slightly less than our significance level of 0.05. So we can conclude that we DO have sufficient evidence to reject the null hypothesis, and there IS a statistical difference between the observed sample mean and population mean.

## Study Design: MechaCar vs Competition

One statistical study that can be performed to quantify how the MechaCar performs against the competition is to test the following metrics: city/highway fuel efficiency of different cars based on vehicle class and safety rating.

* The null hypthesis: the means of all groups are equal
* The alternate hypothesis: at least one of the means is different from all other groups.

To test the hypothesis, we would use ANOVA (two-way) testing. The fuel efficiency would be a numerical, continuous, and normally distributed dependent variable. Vehicle class and safety rating would be categorical independent variables. If safety rating is numerical, the data would need to be converted to factors before performing the ANOVA.

To compare with another population, such as the competition, we would perform paired two-sample t-test, and use the same variables from each population that is being compared.