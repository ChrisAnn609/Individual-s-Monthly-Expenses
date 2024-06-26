# Individual-s-Monthly-Expenses
## Table Of Contents
- [Project overview](#project-overview)
- [Data Sources](#data-sources)
- [Data Cleaning and Preparation](#data-cleaning-and-preparation)
- [Exploratory Data Analysis](#exploratory-data-analysis)
- [Data Analysis](#data-analysis)
- [Results of Findings](#results-of-findings)
- [Recommendations](#recommendations)
- [Limitations](limitations)

### Project Overview
This project aims to analyze the monthly expenses of an individual for the year 2023 across four categories: Groceries, Utilities, Entertainment, and Self Care. The objective is to visualize the overall trend, distribution, and category-wise breakdown of expenses, and to provide recommendations for potential cost-saving measures or areas to budget more effectively. This project is of personal interest as the budgeting of one's expenses allow for better planning for future goals and for any emergencies that may occur.

### Data Sources
The data used for this analysis comes from a CSV file named 'Budget Analysis.csv', which contains monthly expenses for the categories mentioned above.
    
#### The tools used were:
- Excel: For data entry.
- Pandas: For data manipulation and analysis.
- Matplotlib: For creating visualizations.

 ### Data Cleaning and Preparation
In the initial data preparation phase, the following tasks were performed:
- The data was loaded from a CSV file using the pd.read_csv function.
  
```
import pandas as pd
import matplotlib.pyplot as plt

myfile = pd.read_csv("C:\\Users\\Claud\\OneDrive\\Budget Analysis.csv")
print(myfile)

```
- The columns Months, Groceries, Utilities, Entertainment, and Self Care were extracted for analysis.
  
```
x_data = myfile["Months"]
y_data1 = myfile["Groceries"]
y_data2 = myfile["Utilities"]
y_data3 = myfile["Entertainment"]
y_data4 = myfile["Self Care"]

```
### Exploratory Data Analysis

A line plot was used to visualize the trend in the individual's monthly expenses over the year.
```
plt.plot(x_data, y_data1, color="black", marker="*", label="Groceries")
plt.plot(x_data, y_data2, color="red", marker="o", label="Utilities")
plt.plot(x_data, y_data3, color="blue", marker=".", label="Entertainment")
plt.plot(x_data, y_data4, color="purple", marker="_", label="Self Care")

plt.title("LINE PLOT SHOWING THE OVERALL TREND IN MONTHLY EXPENSES FOR THE YEAR 2023")
plt.xlabel("MONTHS OF THE YEAR")
plt.ylabel("AMOUNT IN JMD")
plt.legend()
plt.show()
```
Please see the Line Plot below:

![image](https://github.com/ChrisAnn609/Individual-s-Monthly-Expenses/assets/173093556/ca9520b8-1d25-4fba-b781-981e3b0a7954)


A Bar Graph was used to visualize the total expenses in each category for each month, with different colours representing each category.
```
bar_width = 0.15

x_data1 = range(len(y_data1))
x_data2 = [x + bar_width for x in x_data1]
x_data3 = [x + bar_width for x in x_data2]
x_data4 = [x + bar_width for x in x_data3]

plt.bar(x_data1, y_data1, bar_width, color="black", label="Groceries")
plt.bar(x_data2, y_data2, bar_width, color="red", label="Utilities")
plt.bar(x_data3, y_data3, bar_width, color="blue", label="Entertainment")
plt.bar(x_data4, y_data4, bar_width, color="purple", label="Self Care")

plt.title("BAR CHART SHOWING THE TOTAL EXPENSES IN EACH CATEGORY FOR EACH MONTH")
plt.xlabel("MONTHS OF THE YEAR")
plt.ylabel("AMOUNT IN JMD")
plt.legend()
plt.show()
```
Please see the Bar Graph below:

![image](https://github.com/ChrisAnn609/Individual-s-Monthly-Expenses/assets/173093556/93337d19-46e7-4aff-ae5f-b890ec31ab80)


A Pie Chart was used to show the distribution of total expenses among different categories for the entire year. 

```
plt.pie(total_expenses,labels=categories,autopct="%.2f%%")

plt.title("PIE CHART SHOWING THE DISTRIBUTION OF TOTAL EXPENSES FOR EACH CATEGORY FOR THE ENTIRE YEAR")
plt.legend(loc="best")
plt.show()
```

Please see the Pie Chart below:


![image](https://github.com/ChrisAnn609/Individual-s-Monthly-Expenses/assets/173093556/238ad392-7061-4561-9961-72cfe69c6738)


A Horizontal Bar Graph was created to show the top three categories with the highest total expenses over the year 2023.

```
# Define the width of each bar
bar_width = 0.15

# Adjust x-axis positions for each category
x_data1 = range(len(y_data1))  # For groceries
x_data2 = [x + bar_width for x in x_data1]  # For utilities (shifted by bar_width)
x_data4 = [x + bar_width for x in x_data3]  # For self care (shifted by the bar_width)

# Create the Horizontal bar chart
plt.barh(x_data1, y_data1, bar_width, color="black", label="Groceries")
plt.barh(x_data2, y_data2, bar_width, color="red", label="Utilities")
plt.barh(x_data4, y_data4, bar_width, color="purple", label="Self Care")


plt.title("HORIZONTAL BAR CHART SHOWING THE TOP THREE CATEGORIES WITH THE HIGHEST TOTAL EXPENSES OVER THE YEAR")
plt.xlabel("TOTAL AMOUNT IN JMD")
plt.ylabel("CATEGORIES")
plt.show()
```

Please see the Horizontal Bar Graph below:

![image](https://github.com/ChrisAnn609/Individual-s-Monthly-Expenses/assets/173093556/78b791d9-d560-434a-b295-f999ee1c4ea0)


 
 ### Data Analysis
 
- Based on the Pie Chart, 47.39% of the individual's salary went towards Groceries; whilst 29.16% was spent on Utilities, 21.44% spent on Self Care and the remaining 2.01% went towards Entertainment. The months January, February and November recorded an expense of JMD100,000 for Groceries; whilst the months April, May, June, March and August recorded expenses of JMD120,000, JMD130,000, JMD140,000 and JMD150,000 respectively.
The month of December saw the individual spending the most money spent throughout the year on Groceries-JMD190,000; while in September, the individual spent JMD180,000 on Groceries.

- The amount spent on Utilities for the twelve months of the year fluctuated, as the month of January recorded an expense of JMD80,000, whilst February recorded an expense of JMD85,000. The month of March saw a decline in the amount spent on utilities in comparison to the previous month, with the total spent being JMD80,000. April then saw an increase in the amount spent on utilities to JMD88,000; which then declined for May and June, increased in July and August and continued fluctuating until the month of December, where it gradually increased. 

- The months of July, August and December recorded the highest spent on Utilities, with each of these months recording an expense of JMD100,000. The increase in Utilities in these months could be due to the hot weather in the summer, thus the fan or the Air conditioner is used more frequently than in the other months. The increase in utilities for the month of December could be attributed to the individual being at home for long periods or even inviting family over to enjoy the festive season.

- For the category of Entertainment, irrespective of the Holiday seasons- summer and christmas, the amount consistently spent each month was JMD6000. This is commendable, as it allowed for funds to be allocated to the other categories: Groceries, Utilities and Self Care and even towards savings.

- For the category of Self Care, the amount spent was consistent for the most part; with the months January, February, April-June recording an expense of JMD65,000; while in the months September, October and November, the individual spent JMD45,000 and JMD40,000 on self-care. The months March, July, and December, however, saw a significant increase in expenditure, being JMD78000, JMD79000 and JMD95000 respectively.


### Results Of Findings

- For the category Groceries, the expenses were consistently high, peaking in the months of December and September.
- For the category Utilities, the expenses fluctuated, with peaks in the summer and in  December.
- For the category Entertainment, the expenses were consistent and controlled for the year 2023.
- For the category Self Care, the expenses were stable for the most part, with occasional peaks.

### Recommendations

Based on the analysis, the following actions are recommended:
- Buy items in bulk and consider a lower-cost alternative, such as a  Wholesale. 
- Create a grocery list, so no unnecessary spending is done.
- Plan out meals for the day or week and make purchases based on this meal plan.
- Implement and consistently practice energy saving measures, such as turning off the lights when not in use, checking for any leaking taps or even making use of solar powered bulbs to reduce Utility costs.
- Consider a cheaper alternative as it relates to self care, so more money can be saved.

### Limitations

- Some records had to be excluded, as the accuracy of the analysis conclusion would have been affected.
- The recommendations made are general and may not be applicable to every individual.
  
