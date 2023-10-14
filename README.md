# Python Part 3

# Numpy
NumPy is a module that aims to make calculations in Python lighter. NumPy (Numerical Python): to form and manipulate arrays. NumPy focuses on scientific computing.

## Import Numpy
* import numpy as np

## Checking Numpy Version
* print(np.version)

## Creating a Numpy Array
* arr = np.array([1, 2, 3, 4, 5])
* print(arr)

## Use a Tuple to Create a Numpy Array
* import numpy as np
* arr = np.array((1, 2, 3, 4, 5))
* print(arr)
* print(type(arr))

## Dimensions in Array 
### 0 Dimensions Array
* import numpy as np
* arr = np.array(42)
* print(arr)

### 1 Dimensions Array
* import numpy as np
* arr = np.array([1, 2, 3, 4, 5])
* print(arr)

### 2 Dimensions Array Containing 2 Array
* import numpy as np
* arr = np.array([[1, 2, 3], [4, 5, 6], [7, 8, 9]])
* print(arr)

### 3 Dimensions Array With 2 Dimensions Array Both Containing Two Array
* import numpy as np
* arr = np.array([[[1, 2, 3], [4, 5, 6]], [[1, 2, 3], [4, 5, 6]]])
* print(arr)

### 5 Dimension Array and Verify That Has 5 Dimensions
* import numpy as np
* arr = np.array([1, 2, 3, 4, 5], ndmin=5)
* print(arr)
* print('number of dimension :', arr.ndim)

## Check How Many Dimensions The Array Have
* import numpy as np
* a = np.array(42)
* b = np.array([1, 2, 3, 4, 5])
* c = np.array([[1, 2, 3], [4, 5, 6], [7, 8, 9]])
* d = np.array([[[1, 2, 3], [4, 5, 6]], [[1, 2, 3], [4, 5, 6]]])
* print(a.ndim)
* print(b.ndim)
* print(c.ndim)
* print(d.ndim)

## Get The One Element From The Following Array
* import numpy as np
* arr = np.array([1, 2, 3, 4])
* print(arr[1])

## Get The Third and Fourth Element From The Following Array and Add Then
* import numpy as np
* arr = np.array([1, 2, 3, 4])
* print(arr[2] + arr[3])

## Access The Element On The First Row, Second Column
* import numpy as np
* arr= np.array([[1,2,3,4,5], [6,7,8,9,10]])
* print('2nd element on 1 st row: ', arr[0, 1])

## Access The Element on The 2nd, 5th Column
* import numpy as np
* arr = np.array([[1,2,3,4,5], [6,7,8,9,10]])
* print(arr[1,4])

##  Access The Third Element Of The Second Array Of The First Array
* import numpy as np
* arr = np.array([[[1, 2, 3], [4, 5, 6]], [[7, 8, 9], [10, 11, 12]]])
* print(arr[1, 0, 2])
  
# Pandas
Pandas is a popular open-source data manipulation and analysis library for the Python programming language. It provides easy-to-use data structures and functions for working with structured data, primarily in the form of tabular data, like spreadsheets and SQL tables. Pandas is widely used in data analysis, data cleaning, and data preparation tasks for a wide range of applications, including data science, machine learning, and financial analysis.

## Import the libraries that are needed.
* import pandas as pd
* Pandas (Python for Data Analysis): for data manipulation, data preparation, and data cleaning.
* Pandas has two objects, namely series and data frames

## Object Series
* Object Series has one data dimension, it does not have column names because it only has one column. And it has an index.
 * data = [0.25, 0.50, 0.75, 1]
 * data
 * 
### Convert Data Into Series From
* data = pd.Series(data)
* data

### Convert From Series to Array
* data.values

### Displays Index From Series 
* The index is in the form of a range, where the start point is inclusive of the range and the stop point is exclusive of the range.
* data.index
* list(range(1,10))

### How to Call Data From Series
* data[2]

### Implicit Index
* The implicit index is the default index.
* data['a']
* we can define the index, this is called an explicit index, namely a defined index. when defining indexes, the number of indexes must be equal to the number of data.
* data[3]

### Explicit Index
* This is data selection. Even though we have created an explicit index, we can still call the implicit index. When the implicit index and explicit index are the same, when we call the data, it will only duplicate the explicit index.
* data_2 = pd.Series([0.25, 0.50, 0.75, 1], index=[2,5,3,7])
* data
* Key Errors from data.
* data_2[0]
* We will try to do data slicing.
* data = pd.Series([0.25, 1, 1.75 , 2.25], index=['a', 'b', 'c', 'd'])
* data
* data['b':'c'] # indeks eksplisit
* But if we slice the implicit index, only the starting point will appear, because the implicit index is a range.
* data[1:2] # indeks implisit
* data_2[2:3] #indeks implisit : slicing

## Loc and Iloc
* Loc is for calling its explicit index.
* data_2.loc[3] #selecting indeks eksplisit
* data_2.loc[2:3] #slicing indeks eksplisit
* Iloc is for calling its implicit index.
* data_2.iloc[3] #selecting indeks implisit
* data_2.iloc[2:3] #slicing indeks implisit
### Create Series From Series With Loc and Iloc
* dict_populasi = {'Jakarta':750, - 'Bogor':400, - 'Depok':350, - 'Tanggerang':270, - 'Bekasi':670}
* dict_populasi
* populasi = pd.Series(dict_populasi) #transformasi dictionary ke series
* populasi
* populasi.loc['Depok']
* populasi.iloc[2]

## Data Frame  
* Data Frame is a collection of series, with at least one series.
* daerah = pd.DataFrame({'pop':populasi, 'luas daerah':luas})
* daerah
* daerah['luas daerah']
* daerah['luas daerah']['Jakarta']

## Titanic CSV 
### Load Data Titanic 
* df = pd.read_csv('Titanic.csv')
### Displays Data From Head
* df.head()
### Displays Info Data
* df.info()
### Displays The Number of Rows and The Number of Columns
* df.shape
### Displays Data From Columns
* df.columns
### Displays Data From Index
* df.index
### Displays Information From Columns in The From of Number
* df.describe()
### Displays The Sum Of Not Null From Head
* df.notnull().sum()
### Displays The Sum Is Null From Head
* df.notnull().sum()
### Displays The Amount From Head
* df.sum
### Displays The Mean of Columns
* df['Age'].mean()
### Displays The Median of Columns
* df['Age'].median()
### Displays The Modus of Columns
* df['Age'].mode()
### Displays The Minimal of Columns
* df['Age'].min()
### Displays The Maximal of Columns
* df['Age'].max()

## Mini Project Preparation

