# Module 2
--------

Module 2 is all about importing, filtering/querying, and selecting data with Pandas. Here's a brief overview of some of the key concepts in this regard:

## Importing Data
Pandas can read data from various file formats such as CSV, Excel, SQL, and JSON. It provides the `read_csv()`, `read_excel()`, `read_sql()`, and `read_json()` functions to read data from these sources.

```python
import pandas as pd

df = pd.read_csv('filename.csv')

```

## Filtering Data with loc[] and iloc[]
Filtering data in pandas involves selecting a subset of data based on certain conditions. The loc[] and iloc[] functions are used for filtering data.

loc[] is used to select rows based on a label or a boolean array. For example, to select rows where the 'age' column is greater than or equal to 30, you can use the following code:

```pythyon
df.loc[df['age'] >= 30]

```
iloc[] is used to select rows based on integer indexing. For example, to select the first three rows, you can use the following code:

```python
df.iloc[:3]
```

## Selecting Columns 

In pandas, you can select columns of a DataFrame using single square brackets [] or double square brackets [[]] aka "bracket bracket".

Using single square brackets [] returns a **Pandas Series object**, while using double square brackets [[]] returns a **DataFrame object**.

Here's an example:

```python
import pandas as pd

df = pd.DataFrame({
    'name': ['Alice', 'Bob', 'Charlie'],
    'age': [25, 30, 35],
    'city': ['New York', 'Paris', 'London']
})

# using single square brackets [] returns a Pandas Series object
ages = df['age']
print(ages)



# using double square brackets [[]] returns a DataFrame object
df_subset = df[['name', 'city']]
print(df_subset)


```

## Filter rows with query()

The query() method makes it easy to write complex filters and expressions in a readable and concise way. It also allows you to refer to columns in your DataFrame directly by name, without needing to use the df['column_name'] syntax.

The query() method is particularly useful when you need to filter a large dataset based on multiple conditions. It can also help you to avoid common errors that can arise from using multiple boolean operators and parentheses.

```python
import pandas as pd

# create a sample DataFrame
df = pd.DataFrame({
    'name': ['Alice', 'Bob', 'Charlie', 'David', 'Emma'],
    'age': [25, 30, 35, 40, 45],
    'gender': ['F', 'M', 'M', 'M', 'F'],
    'city': ['New York', 'Paris', 'London', 'San Francisco', 'Sydney']
})

# use the query method to select only the rows where age is greater than 30 and gender is 'M'
df_filtered = df.query('age > 30 and gender == "M"')

# print the filtered DataFrame
print(df_filtered)

```

In this example, we created a sample DataFrame with columns for name, age, gender, and city. We then used the query() method to select only the rows where age is greater than 30 and gender is 'M'. The resulting DataFrame, df_filtered, contains only the rows that meet these conditions.

