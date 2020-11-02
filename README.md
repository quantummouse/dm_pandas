# First Data Mining Assignment Data 612

Using Google Collab notebooks and pandas, look at different Pandas
commands and what they can do.

## Installation

Using this data source [State Drug
Utilization](https://github.com/frankData612/data_612/blob/master/State_Drug_Utilization_Data_2010$
and importing pandas, you can then do all the data exploration.


```bash
import pandas as pd
```

## Usage
Assignment 1
```python
import foobar

df.head(4) # returns 4 rows in the top
df.tail(4) # returns 4 rows in the bottom
for col in df.columns: print(col) # prints all the columns
type(df) # type of dataset
df.dtypes # type of the objects in the dataset
df.shape # will tell you how many rows and columns
df.columns = df.columns.str.replace(' ','_')
print(df.columns) # to print column names, the space needs to be
replaced
avg_size = df.groupby('State')['Total_Amount_Reimbursed'].mean()
print(avg_size) # printing average number per state
```
Assignment 2
```python
#import python and numpy 
#import the date set from https://raw.githubusercontent.com/chendaniely/\
pandas_for_everyone/master/data/scientists.csv'
# Convert the column all to the datetime format specifying the format you want
birthdayDate = pd.to_datetime(birthday, format = '%Y-%m-%d')
#Fiding maximum date and calculating the difference - it propogates down the whole column
maxDate = max(birthdayDate)
difference = maxDate - birthdayDate
#converting the difference in time to months using numpy
diffMonths = difference / np.timedelta64(1, 'M')
#Adding column to the data frame
scientists['diffInDate'] = diffMonths
#Converting the file to csv
scientists.to_csv('scientists_clean.csv', index=False)


Assignment 3
```python
#import all the dependencies, including seaborn and pyplot
#using same data from the google drive about medicaid vs. non medicaid reimbursements
#barplots were helpful at seeing differences and number of prescriptions, per state or reinbursement type.
g = sns.barplot( "Total Amount Reimbursed", "State", data=drugsutil, order=pd.value_counts(drugsutil['State']).iloc[:10].index)
#iloc[:10] helped show only 10 of the top selections
#catplot showed some fo the numbers well, and it is possible to control different aspects of the chart
#scatterplot was easy to generate and showed that large number of prescription of a drug didn't necessarily translate into reimbursement
#charts showed a lot of prescriptions written for hydrocodon whcih is an opiod. While it had the most prescriptions, it didn't have the most reimbursements.
#The highest reimbursements were for Risperidone, a mental health drug.

```
Assignment 4
```python
#Import another data set. In this case, I imported data set with only Ohio drug utilization medicaid data for year 2020. Drug_Utilization_2020_-_Ohio.csv
#Merging was hard as Collab Notebooks have a limit on Ram and these data sets have millions of rows. So data set size matters in the Collab. 
#I merged all the data , so now there would be more data with year 2020 and Ohio only , which would also generate more Null values. 
result = pd.merge( drugsutil, drugsutil2020, how="outer")
# There are many ways to do this - I found nulls and turned them into word "Missing" 
np.count_nonzero(result.isnull()
result.fillna('Missing')
#I didn't delete the missing data as it would not add anything to the dataset in the future. If I were to delete rows with missing data, that's a lot of data gone.
#Using a string to define it, I can later count them or exclude them by this value from any data counts or visualizations. 

```


## Contributing
It's an assignment.

## License
[MIT](https://choosealicense.com/licenses/mit/)
