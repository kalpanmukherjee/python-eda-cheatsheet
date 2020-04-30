# Python - Exploratory Data Analysis CheatSheet

### Reading a CSV file
Use _header=None_ when the columns are not labeled in your csv file
```python
df = pd.read_csv("pathToFile.csv", header=None)
```
### Reading an Excel(.xlsx) file
Use _header=None_ when the columns are not labeled in your xlsx file
```python
df = pd.read_excel("pathToFile.xlsx", header=None)
```
### Show first 5 rows of a DataFrame
```python 
df.head()
```
### Show last 5 rows of a DataFrame
```python
df.tail()
```
### Show all column names in the DataFrame
```python
df.columns
```
### Count occurances of all unique values in a column
```python
df['column_name'].value_counts()
```
### Show mean, std dev, max etc for each column
```python
df.describe()
```
### Show sum of all null/NaN rows in each column
```python
df.isnull().sum()
```












