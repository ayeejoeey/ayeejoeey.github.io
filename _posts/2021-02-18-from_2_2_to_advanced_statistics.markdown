---
layout: post
title:      "From 2+2 to Advanced Statistics"
date:       2021-02-18 23:22:56 +0000
permalink:  from_2_2_to_advanced_statistics
---


Now I'm not saying that before learning advanced statistics all I knew was simple addition....  I knew multiplication as well. *insert laughing emoji* .

On a more serious note, I've recently touched based on statistics unlike I've ever had before. And I only scratched the surface. My name is Joe and I've just finished Module 2 of the Data Science curriculum by Flatiron School. At the end of the module, I was presented a project which required me to predict the prices of homes for King County located in Washington, by using a multiple linear regression model. Although, learning as much as I did through out the module, I learned the most while working on the project. The project forced me to put what I learned, to use. This being, cleaning and analyzing data, dealing with categorical values, dealing with non-categorical values, checking for normalization and multicollinearity, and on and on and on. To where eventually I ended up with a final model with an R^2 of 65% and about 25 predictors. To elaborate a little more on my methodology, I'll make some bullet points.

* Data cleaning (dealing with outliers and null values)
* Data processing: Dealing with categorical values (creating dummy variables, binary format conversions)
* Data processing: Dealing with non-categorical values (normalizing and dealing with multicollinearity)
* Ordinary Least Squared (OLS) Modeling
* Validating regression assumptions (linear, normality, qqplots, heteroscedasticity)
* Plots used: regplot, boxplot, barplot, histplot, qqplot, scatterplot

I hold some pride to this because If you were to tell me these are the methods I used for a project a couple months ago, I wouldn't have understood any of those. But, let me humble myself, I'm still learning a lot. Everyday that I worked on my project, I either learned something new, or gained more comprehension of something I learned previously.

Math is not my strong suit. I definitely struggled for the first few sections of the module. I started writing notes to reinforce the mathematical concepts that went into builing a mulitple linear regression model. I outsourced to gain more information and knowledge on the sections I was working on. I realized that when it comes to mathematics, vizualizations help me understand so much more than just words. Sometimes I need things to be drawn out for me like I'm 5 years old to understand. But hey, I'm not complaining, whatever works.. works. 


I want to share with you a vizualization that I was proud of. This vizualization displays each predictor and its correlation to price. 

```
# These next few lines of code will create a dataframe of predictors and their correlation with the target variable 'price'
# This block of code will be used frequently through the preprocessing and final modeling
# assign the predictors to x and assign the target variable to y
x = df.drop(columns=['price'], axis=1)
y = df['price']

# create a list for the coefficient correlation to price
correlation_to_price = []
# iterate through each column in x and append the coefficient correlation value to the list
# stats.pearsonr(x,y) returns the coefficient correlation and p-value for each predictor, however we just want to collect
# the coefficient correlation using [0]
# round the coeifficient values to 2
for col in x.columns:
    correlation_to_price.append(round(stats.pearsonr(x[col],y)[0],2))

# next we need to assign the coefficient corr. values to a dictionary along with their corresponding column names
# create a dictionary
correlation_dict={}
# iterate and match each column with its coefficient correlation
for i, c in zip(x.columns,correlation_to_price):
    correlation_dict[i] = c

# finally create a dataframe for the predictors and correlation
df_correlation = pd.DataFrame(sorted(correlation_dict.items(),key=lambda x:x[1],reverse=True),columns=['predictors','correlation'])

```

```
df_correlation
```

![](http://Screen Shot 2021-02-18 at 3.21.30 PM.png)


