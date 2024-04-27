python good practices :
- all or any
- zip
- ternary operator : `value_if_true if condition else value_if_false`
- enumerate
- list comprehension
- lambda functions
- use and read about `decorators and generators`
- multiple Function Arguments : use of `(*args, **kwargs)`
- dictionary comprehensions
- Lists, sets, and dictionaries are mutable : Mutable means that we can change or update the object(list, set, or dictionary) without changing the pointer of the object in the memory.

##### Pandas Quick Guide

- Read dataset :`df = pd.read_csv('path_to,_csv_file', sep = "separator_value")`
- display all columns : `df.columns`
- get details of the dataframe : `df.info()`
- get  the statistics of the data in the DataFrame such as count,mean,standard deviation etc. : `df.describe()`
- slicing the dataframe : `df[x:y]` where x and y are index position values , exclusive of y, inclusive of x. This is row wise indexing
- access data with index value : `df.loc[index_value]` or `df.iloc[index_value]`
- diff between loc and iloc : `loc` gets rows (or columns) with **particular labels** from the index. While  `iloc` gets rows (or columns) at **particular positions** in the index (so it only takes integers). #TODO Read up more about it and do some hands-on
- display the top x rows : `df.head(x)` , by default x = 5 for `df.head()`
- drop columns from the dataframe : `df.drop(["col_1", "col_2", ], axis = 1)`
- get unique values used for a column : `df["column_name"].unique()`
- get the number of unique values for a column : `df["column_name"].nunique()`
- get the count of different values in single column that is taken : `df["column_name"].value_counts()` or `df.col_name.value_counts()`  . Note : value_counts() does not count NaN (missing) values.
- Rename the columns : `df_new = df.rename(columns={‘current_column_name’:’new_column_name’})
- check for data types of the columns : `df.dtypes`
- merge dataframes : 
- join dataframes : 
- use map on dataframe : `df["col_name"] = df["col_2"].map(lambda function)`
- use apply function to the dataframe : `df["col_1"] = df["col_2"].apply(python_function)`
- Filter the DataFrame using conditions.
- create a copy of the dataframe : `df_new = df.copy()`
- To know different types and count of data that is present in DataFrame : `df.dtypes.value_counts()`
- leverage regex on dataframes : eg --> `df_new = df_new.replace(r’^\s*$’, np.NaN, regex=True)`
- get the null values count for each feature / column in the dataframe : `df_new.isnull().sum()`
- check for missing values in a column : `df.isna().any()`
- replace rows with NaN or missing values : `df_new1=df_new.replace(np.nan,0)` or `df_new2=df_new.fillna(0)`
- removing or applying `df.replace` or `df.fillna` at column level : `df["col_name"] = df["col_name"].fillna(any logic {eg. df["col_x"].mean()})`
- **axis** parameter is used to select row (0) or column (1).
- replace values in rows or columns based on a condition : `df[col_name].where(condition, new_value)` , default is NaN
- create a dataframe from dictionary : `df = pd.DataFrame({'key_1' : [val1, val2, val3], 'key_2' : [val1, val4, val5]})`
- show the number of rows and columns of the dataframe : `df.shape`
- sort values by column = `df.sort_values(by = "column_name", ascending = True/False)`
- rename column names = `df.rename(columns = {key-value dict with key as old name and value as new name})`
- change data type of a column with `astype(data type value)` function . eg. df.column.astype("int")
- understand table reshaping :
  - `pd.concat([df1, df2], axis = 0)` --> concatenate along x axis
  -  `pd.pivot(index, columns, values)`
- [ref](https://freedium.cfd/https://medium.com/wicds/a-comprehensive-guide-to-pandas-for-data-science-64ed1be1bafe)
- [Leetcode Pandas Questions](https://leetcode.com/studyplan/introduction-to-pandas/)
- using conditional filtering in Pandas :
  1. 


##### English SDK for Apache Spark
- Leverage GenAI to compile natural language( English) into PySpark and SQL Code
- The English SDK simplifies Spark development process by offering the following key features:

	- **Data Ingestion:** The SDK can perform a web search using your provided description, utilize the LLM to determine the most appropriate result, and then smoothly incorporate this chosen web data into Spark—all accomplished in a single step.
	- **DataFrame Operations:** The SDK provides functionalities on a given DataFrame that allow for transformation, plotting, and explanation based on your English description. These features significantly enhance the readability and efficiency of your code, making operations on DataFrames straightforward and intuitive.
	- **User-Defined Functions (UDFs):** The SDK supports a streamlined process for creating UDFs. With a simple decorator, you only need to provide a docstring, and the AI handles the code completion. This feature simplifies the UDF creation process, letting you focus on function definition while the AI takes care of the rest.
	- **Caching:** The SDK incorporates caching to boost execution speed, make reproducible results, and save cost.
- 