> # ***EXPERIMENT 3: PYTHON DATA ANALYSIS (PANDAS)***

> **Name**: Joshane Eunice M. Faustino
>
> **Section**: 2ECEC
> 
> **Date**: September 3, 2026
> 
 **I. Intended Learning Outcomes**
 
At the end of this laboratory activity, the student should be able to:

1. load a CSV dataset into a Pandas DataFrame;
2. select rows and columns using positional and label-based indexing;
3. filter records using conditions on a DataFrame column; and
4. extract a well-defined subset of data without changing the source data.
> # What is pandas?
- short for **Python Data Analysis**
- it is a core Python library that provides high-performance,
easy-to-use data structures and data analysis tools
for the Python programming language.
- this is used for this programming assignment
> # Process
**- Pandas as pd was imported in order to access the library pandas and to also shorten pandas  
instead of typing it multiple times import pandas as pd**

```cars = pd.read_csv("cars.csv")```

The ***pd.read*** function in Pandas is used to read data from CSV files into a Pandas DataFrame.
# **A - POSITIONAL AND LABEL-BASED SLICING**
a. Display the shape and complete list of column names of cars.

**CODE:**
```shape = cars.shape```

result: (32, 12)
The ***.shape*** function is used to display the number of dimensions in a data frame or set of arrays.

b. Using positional slicing, create cars 6 to 10 containing rows 6 through 10 of the dataset, where
the first data row is row 1

**CODE:**
```cars_6_to_10 = cars.iloc[6:11, 0:12]```

The code ***.iloc*** is used for integer-location-based indexing — meaning you select rows and columns by their numerical position (starting from 0), not by labels.
- This code means having rows 6 to 11 and columns 0 to 12 while performing slicing
- ```dataframe.iloc [<row selection>], [<row selection>]```
- Slicing a Pandas DataFrame is an important skill for extracting specific data subsets. Whether selecting rows, columns or individual cells,
  
c. From cars 6 to 10, display only the columns Model, mpg, cyl, hp, and gear, in that order.

**CODE:**

```cars_6_to_10.loc[0:0,['Model','mpg', 'cyl', 'hp', 'gear']]```
- ```dataframe.iloc``` is to select single value by row & column labels
- cars_6_to_10 is the data frame to locate
  
# **B - MODEL LOOKUP**

a. Display the complete row for Toyota Corolla.

**CODE:**

```toyota = cars.loc[(cars['Model'] == 'Toyota Corolla')]```

- Boolean indexing in Pandas allows you to filter data based on conditions applied to a DataFrame or Series. This is particularly useful for extracting rows or columns that meet specific criteria.
-```The cars.loc[(cars['Model'] == 'Toyota Corolla')]``` command in Pandas is used to filter a DataFrame cars based on the condition that the Model column contains the value 'Toyota Corolla'.
- This command means that upon reading cars, it will locate cars' models and if Toyota Corolla is found and true, it will show it.
- This command selects all rows where the model name matches 'Toyota Corolla', allowing for the extraction of specific data from the DataFrame.
- The loc method is a label-based indexing method, which means it uses the names of the rows and columns to access the data.
- This method is particularly useful when the DataFrame has a hierarchical index, as it allows for easy selection of rows and columns by their labels. 


b. For Pontiac Firebird, display only Model, mpg, hp, and wt.

**CODE:**

```pontiac = cars.loc[(cars['Model'] == 'Pontiac Firebird', ['Model', 'mpg', 'hp', 'wt'])]```
- This is the same as boolean indexing in which it will only display if the condition is true which turned out to find Pontiac Firebird along the column model.
- After that, it is asked to display the columns as follows ```['Model', 'mpg', 'hp', 'wt']``` but specifically that model name only

# **C -  MULTI-MODEL SUBSETTING** 

Create a DataFrame named selected cars containing only the records for three models: Datsun 710,
Lotus Europa, and Ferrari Dino.

For these records, retain only Model, mpg, cyl, hp, and gear. Select the rows by their model values
rather than by row numbers. 

**CODE:**

```selected_cars = cars.loc[(cars['Model'] == 'Datsun 710', ['Model', 'mpg', 'cyl', 'hp', 'gear'])]```

- This code used boolean again and located the car model Datsun 710 but only retained the following columns, ['Model', 'mpg', 'cyl', 'hp', 'gear']

Display selected cars and its shape.

```selected_cars.shape```

result: (1, 5)
