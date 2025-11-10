Pandas has two built-in data types: **series** and **data frame**

## Function: 

1. db.info(): what types are used
2. db.describe(): overview of the numerical data, gives the most important statistical analysis.
3. pd.to_numeric(db[column], error={'ignore','raise','coerce'}, downcast={'integer','signed','unsigned','float'}): ensure every entry in a column is numeric.
4. db[column].isna(): by checking which values are NaN, with True and False values.
5. db.dropna(axis, how, subset, thresh): drop rows if any values is NaN
6. db.fillna(value, method, axis, limit): replace NA with mean, max or min values of the column, strings and 0.
7. db.nunique(): how many unique values we have in each column of the Dataframe.
8. db.duplicated(): To search for entire rows of data that duplicate other rows, and return a mask
9. pd.concat(df, axis, join):append one data structures to the other along one axis
10. pd.merge(dataframe1. dataframe2. on, how): Merge two dataframes by one or multiple Keys/ Indices, A little bit like Join in SQL


Fact:

1. type(np.NaN) = float, which means coerce a column can apply all numeric operations to entire columns.
2. mask is a series return True and False
3. ~ will revert boolean values in a series
