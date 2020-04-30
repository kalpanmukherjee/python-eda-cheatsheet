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
### Show shape of the dataframe
```python
df.shape
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
### Show datatypes for all columns
```python
df.info()
```
### Heat Map of where and which columns has null/NaN values
NOTE: *import seaborn as sns*
```python
sns.heatmap(df.isnull())
```
### Drop multiple columns at once
*axis=1* is for columns 
```python
df.drop(['column_1','column_2'],axis=1,inplace=True)
```
### Fill NaN values with mean value of a column
```python
df['column_name']=df['column_name'].fillna(df['column_name'].mean())
```
### Get numerical values for categorical data
```python
df['column_name'] = pd.factorize(df['column_name'])[0]
```
### Get all unique calues in categorical data
```python
unique = pd.factorize(df['column_name'])[1]
```
### Convert column to float data type
```python
df['columns_name'] = df['column_name'].astype("float")
```













