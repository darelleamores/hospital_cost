# Hospital Revenue Analysis 

Using Excel, analyzing de-identified hospital to answer questions to answer several goals hospital project goals to further help increase production efficiency

# Objectives 

1. To record the patient statistics, the agency wants to find the age category
of people who frequent the hospital and have the maximum expenditure.
2 In order of severity of the diagnosis and treatments and to find out the
expensive treatments, the agency wants to find the diagnosis related group
that has maximum hospitalization and expenditure.
3. To properly utilize the costs, the agency has to analyze the severity of the
hospital costs by age and gender for proper allocation of resources.
4 Since the length of stay is the crucial factor for inpatients, the agency wants
to find if the length of stay can be predicted from age, gender, and race.
5. To perform a complete analysis, the agency wants to find the variable that
mainly affects the hospital costs.

All Analysis is done in Excel

# Goal 1: To record the patient statistics, the agency wants to find the age category of people who frequent the hospital and have the maximum expenditure.

Let’s do a PIVOT table that shows the most common age group 

![3  Pivot_table_of_age_total_charges_avg_total_charges](https://user-images.githubusercontent.com/50031745/218300031-d88a1a5f-5d53-42da-8fca-467358fb1a58.JPG)

We see that Age 0 has the most charges because that age dominates the population of the hospital, so let’s bring in the average charge.
So every 3 year that came to this hospital, had a average charge of 10 grand. Every 9 year old that came to the hospital had the average total charge of 10 grand. 

# Goal 2: In order of severity of the diagnosis and treatments and to find out the expensive treatments, the agency wants to find the diagnosis related group that has maximum hospitalization and expenditure.

We need a table that lists diagnosis group and we want maximum hospitalization which means length of stay and then the associate expenditure associated with that. 
Make a new Pivot Table – let’s pull in Diagnosis Code as the rows, Count of Diagnosis Code, Average Length of Stay, Sum of Total Charge, Average of Total Charge.
Pull in length of Average Length of Stay and Average of TotalCharg2.

![3  Pivot_table_of_diagnosiscode_countdiagnosiscode_avglengthofstay_sumtotalcharges_avg_total](https://user-images.githubusercontent.com/50031745/218300127-1989aadb-c467-400a-9a7c-1d025a4243f1.JPG)

![4  Scatchtable](https://user-images.githubusercontent.com/50031745/218300132-e142da46-0810-44cf-a376-dd9d95f44918.JPG)

Now we use the scartchtable to prepare the ScatterPlot 

![5 Scatterplot Avg Charge Vs LOS](https://user-images.githubusercontent.com/50031745/218300151-e5681a78-a827-4c74-85d7-f5a2f8eaa0c5.jpg)

We see from the Graph that the Average Length of Stay is relatively short but has a high average cost for that service. For everything in this upper left quadrant is going to be high cost and low length of stay.  On the otherhand, people that sit on the hospital 42 days or so and they get out paying 30 grand and it’s still a lot of money – 40 days of service. It’s nothing like being in the hospital for 40 grand. 
The Highest amount of being paid about $48,333 which is diagnostic code 911.

# Goal 3: To properly utilize the costs, the agency has to analyze the severity of the hospital costs by age and gender for proper allocation of resources.

Let’s make a new Pivot Table – Female, Charges Twice

![6  Pivot_table_female_avgcharg_sumcharg](https://user-images.githubusercontent.com/50031745/218300194-561ccc06-4630-4fcf-883f-e67bb053fd98.JPG)

From seeing the table and Conditionally format on each Quandrant. We see the charge basis across both sexes males and female that age zero is the highest ands we know why there were 267 patients of that age – it is no surprise. But now let’s look now, looking at averaghe charge. For males, it is age 3 year old, 11 grand. However, for females – it is females that paid roughly 10 grand. In the total basis, males pay 3 grand in average charges and females pay 25k which a little bit less in average charges. 

# Goal 4: Since the length of stay is the crucial factor for inpatients, the agency wants to find if the length of stay can be predicted from age, gender, and race.

What they are talking about here is multiple regression! So want to predict length of stay, age, and female. For race remember they have the data is coded 1 through 6. When we’re looking at regression modeling, we don’t need like the number 1 is greater than the other numbers. So we need to code it out to a dumby variable to make it work. Use formula =IF(D2=1,1,0) (if race =#, then give us a 1, if not give us a 0). We use this new table for Multiple Regression! 

![new_table](https://user-images.githubusercontent.com/50031745/218300250-b502d5d5-39c1-4ea1-a621-c6da3a7d9ffb.png)

Now go to Data > Data Analysis > Regression

Dependent Variable: Length of Stay ( What do want to predict) 
Independent Variables: 	Age, Female,Race1, Race2,Race3,Race4,Race5,Race6

![7  Regression Analysis](https://user-images.githubusercontent.com/50031745/218300277-fab75669-8759-4ef7-b429-6484f2a18df2.JPG)

We see that non of the variables are not significant of length of stay because of the p-values are not less than .05. We can conclude that no you cannot predict length of stay from of all these variables. 	

# Goal 5: To perform a complete analysis, the agency wants to find the variable that mainly affects the hospital costs.

Now we’re adding Total charges – because of hospital cost to our multiple regression analysis table. 

Dependent variable: Total Charge
Independent Variable: Length of Stay, Age,Female,Race

![7  Regression Analysis_2](https://user-images.githubusercontent.com/50031745/218300303-bc802d20-c441-48c1-8b2a-5870438fab3c.JPG)

We see that Length of Stay, Age, and Sex is a good predictor of Total Charge that mainly affects the hospital costs. When we’re looking at these three statistically is this.  

Looking at the coefficients, for intercept – someone is going to be charge $679 before how long they are there before the other coefficients. For Length of stay we have $742 increase per day of the length of stay. For Age we have a $114 increase per year of age increase – as you get older, you pay more. For FEMALE(sex), if you are a female – you will be charge on average $1000.00 less if you were male. 





