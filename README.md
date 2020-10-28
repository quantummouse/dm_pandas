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


## Contributing
It's an assignment.

## License
[MIT](https://choosealicense.com/licenses/mit/)
