Pandas is a software library written in python programming language for data manipulation and analysis. In particular it offers data manipulation and operations for manipulating numeric tables and timeseries.

Pandas has several Data structures,  but the 2 most commonly used are:
1. Dataframe - its a tabular dataset with rows and columns
2. Series - it is a single row/column created from data frame


For understanding different functions and attributes of Pandas DF and Series, I've created this Colab notebook, sitting in my google drive, 10abhishek10@gmail.com : [link](https://colab.research.google.com/drive/1-i8bm_Rveuv29HW2buK7m_h1FX0Wa9i9)

The data set utilized in this notebook is sitting in my GIT repository : "GitHub\Ml-problem-framework\Datasets for practice\IPL match Dataset.csv"

For GroupBy function, we're also using IPL_Deliveries_Dataset.csv
sitting at same location

as collab deletes the dataset after runtime clears, reupload it incase you need to rerun the reports.





























Note
any data type can have functions or attributes. Functions are generally functions in the datatype class, which ideally have parameters that can be modified according to requirements.
For Example for pandas data frame df
df.head() is a function, by default it prints 5 values but it can take a value to customize number of values to print.

But an attribute on the other hand is fixed and does not need ()
ex: df.shape