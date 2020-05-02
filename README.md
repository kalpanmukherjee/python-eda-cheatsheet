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
### Show datatypes for all columns
```python
df.info()
```
### Show sum of all null/NaN rows in each column
```python
df.isnull().sum()
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
### Get unique values in any column
```python
df['column_name'].unique()
```
### Convert column to float data type
```python
df['columns_name'] = df['column_name'].astype("float")
```
### Make existing column the index
```python
df = df.set_index(df['column_name'])
```
### Get subset of df where column value is equal to some value
```python
df_bangalore = df[df['city']=='bangalore']
df_lucknow = df[df['city']=='lucknow']
```

### Show all indexs in the dataframe
```python
df.index
```
### Convert dataframe to numpy array 
NOTE: Column names are ignored and only float/integers allowed
```python
df.to_numpy()
```
### Sort values by a column 
```python
df.sort_values(by='colName')
```
### Copy a whole dataframe
```python
df.copy()
```
### Drop the rows which have Nan values
```python
df.dropna()
```
### Replace Nan values with a specified value
```python
df.fillna(value=10)
```
### Return a dataframe of boolean values to check Nan values
```python
pd.isna(df)
```
### Calculate the mean of each column
```python
df.mean()
```
### Calculate the mean of each row
```python
df.mean(1)
```
### Concatenate dataframes
```python
pd.concat([df[:2],df[3:6]])
```
### Merge two dataframes with a custom index
```python
pd.merge(df1,df2,on='indexColName')
```
### Groupby column and sum
```python
df.groupby('colName').sum()
```
### Subtract all columns by a specific column
```python
df.subtract(df['col'],axis=0)
```
### Save a dataframe to csv file
```python
df.to_csv('filename.csv')
```
### Save a dataframe to excel sheet
```python
df.to_excel('filename.xlsx',sheet_name='Sheet1')
```
### Label Encoding
Will change categorical data into one column of integer data
```python
from sklearn.preprocessing import LabelEncoder
label_encoder = LabelEncoder()
integer_encoded = label_encoder.fit_transform(df['column_name'])
```
### One hot encoding / Get dummies
```python
df_processed = pd.get_dummies(df, prefix_sep="__",columns=["column_1", "column_2"])
```
### Standard Scaling
NOTE: Make sure you use *fit_transform* only on train dataset and use just *transform* for test and post-deployment dataset
```python
from sklearn.preprocessing import StandardScaler
scaler = StandardScaler()
train_data = scaler.fit_transform(train_data)
test_data = scaler.transform(test_data)
```

                              











