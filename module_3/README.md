# Module 3
----

In Pandas, the groupby() function is used to group data in a DataFrame based on one or more columns, and the agg() function is used to apply aggregate functions to the grouped data. Together, these functions make it easy to perform complex data manipulations and calculations on large datasets.

The groupby() function allows you to group data in a DataFrame by one or more columns. For example, you could group a DataFrame of sales data by the region column to get the total sales for each region. Once you have grouped the data, you can use the agg() function to apply aggregate functions to each group. Aggregate functions include sum(), mean(), min(), max(), count(), and many others.

Here's an example of how to use groupby() and agg() together to perform calculations on a DataFrame:

```python

import pandas as pd

# create a DataFrame of sales data
df = pd.DataFrame({
    'region': ['East', 'East', 'West', 'West', 'South', 'South'],
    'product': ['A', 'B', 'C', 'D', 'E', 'F'],
    'sales': [100, 200, 300, 400, 500, 600]
})

# group the data by region and product, and calculate the total sales for each group
totals = df.groupby(['region', 'product']).agg({'sales': 'sum'})

# print the resulting DataFrame
print(totals)

```

## Method chaining 

Method chaining in Pandas is a technique for applying multiple operations to a DataFrame or Series in a single line of code. Instead of writing each operation on a separate line, method chaining allows you to chain multiple operations together using the dot . notation.

```python
import pandas as pd

# create a DataFrame of sales data
df = pd.DataFrame({
    'date': ['2022-01-01', '2022-01-01', '2022-01-02', '2022-01-02'],
    'product': ['A', 'B', 'A', 'B'],
    'sales': [100, 200, 300, 400]
})

# group the data by product, calculate total sales, and sort in descending order
result = df.groupby('product')['sales'].sum().sort_values(ascending=False)

# print the resulting Series
print(result)

```

In this example, method chaining is used to perform three operations on the DataFrame in a single line of code. First, we grouped the data by product using groupby('product'). Then we calculated the total sales for each product using ['sales'].sum(). Finally, we sorted the results in descending order using .sort_values(ascending=False).

to make this more readable we can wrap this in parenthesis ()

```python
# group the data by product, calculate total sales, and sort in descending order

result = ( df
           .groupby('product')['sales']
           .sum()
           .sort_values(ascending=False)
           )
```

To me this is infinately more readable than dumping everything on one line. 

```
