# Homework Assignment Instructions

## Overview

Do not be discouraged if you don't succeed at everything immediately. The work of every data analyst is closely related to searching and researching, so it is very important to learn how to find the necessary information and adapt it to your needs. If you have any questions, you can also contact your mentor.

## Part One: Introduction to Pandas

### Tasks:
1. Read data using the `read_html` method from the table "Birth Rate in Ukrainian Regions (1950-2019)" from provided links.
2. Display the first rows of the table using the `head` method.
3. Define the number of rows and columns in the dataset (use the `shape` attribute).
4. Replace the `"—"` value in the table with NaN.
5. Define the types of all columns using `dataframe.dtypes`.
6. Change the types of non-numeric columns to numeric. Hint: these are columns that contained the `"—"`.
7. Calculate the proportion of empty places in each column (use `isnull` and `sum` methods).
8. Remove data for the entire country, which is the last row of the table.
9. Place missing data in columns with average values of those columns (using `fillna`).
10. Obtain a list of regions where the birth rate in 2019 was higher than the average for Ukraine.
11. Which region had the highest birth rate in 2015?
12. Build a bar chart of the birth rate by regions for 2019.

Submit the assignment as a Jupyter Notebook file named `Hw2.1.ipynb`.

## Part Two: File Analysis

### Tasks:
1. Read the file `2017_jun_final.csv` using the `read_csv` method.
2. Display the first rows of the table using the `head` method.
3. Define the size of the table using the `shape` method.
4. Define the types of all columns using the `dataframe.dtypes` method.
5. Calculate the proportion of empty spaces in each column (use `isnull` and `sum` methods).
6. Remove all columns with spaces except for the "Programming Language" column.
7. Recount the percentage of empty spaces in each column and ensure only the "Programming Language" column remains.
8. Remove all rows from the original table using the `dropna` method.
9. Define the new size of the table using the `shape` method.
10. Create a new table `python_data` containing only rows with specialists who listed Python as a programming language.
11. Define the size of the `python_data` table using the `shape` method.
12. Using the [groupby](https://pandas.pydata.org/docs/reference/api/pandas.DataFrame.groupby.html) method, group by the "Role" column.
13. Create a new DataFrame where, for data grouped by the "Role" column, you perform data aggregation using the [agg](https://pandas.pydata.org/docs/reference/api/pandas.DataFrame.agg.html) method and find the minimum and maximum values in the "Monthly Salary" column.
14. Create a function `fill_avg_salary` that returns the average monthly salary. Use it in the [apply](https://pandas.pydata.org/docs/reference/api/pandas.DataFrame.apply.html) method to create a new column "avg".
15. Create descriptive statistics using the `describe` method for the new column.
16. Save the resulting table to a CSV file.

Submit the assignment as a Jupyter Notebook file named `Hw2.2.ipynb`.

## Part Three: Dataset Analysis with Kaggle.com

In this part of the homework, we will delve deeper into the pandas library and look at more advanced functions.

### Tasks:
1. Read the csv file (use the `read_csv` function).
2. Display the first five rows (use the `head` function).
3. Display the dimensions of the dataset (use the `shape` attribute).
- **Question:** How many books are data stored for in the dataset?
4. There are 7 variables (columns) available for each of the books. Let's take a closer look at them:

    - Name — name of the book
    - Author — author
    - User Rating — user rating (on a 5-point scale)
    - Reviews — number of reviews
    - Price — price (in dollars as of 2020)
    - Year — the year the book made it into the Top 50
    - Genre — genre

To simplify your work, change the variable names slightly. As you can see, all names start with a capital letter, and one of them even includes a space. This is very undesirable and can be quite inconvenient. Change the case to lowercase, and replace the space with an underscore (snake_style). At the same time, get to know a useful dataframe attribute — columns (you can simply assign a list of new names to this attribute):
    ```python
    df.columns = ['name', 'author', 'user_rating', 'reviews', 'price', 'year', 'genre']
    ```

# Data Exploration and Analysis

## Initial Data Exploration

### Tasks:
1. Check if all rows contain a sufficient amount of data: print the number of empty places (`na`) in each column using the `isna` and `sum` functions.
   - **Question:** Are there any variables with missing values? (Yes / No)
2. Check the unique values in the 'genre' column using the `unique` function.
   - **Question:** What are the unique genres?
3. Examine the price distribution: build a histogram (use `kind='hist'`).
4. Determine the maximum, minimum, average, and median prices using the `max`, `min`, `mean`, `median` functions.
   - **Questions:**
      - Maximum price?
      - Minimum price?
      - Average price?
      - Median price?

## Data Searching and Sorting

1. Answer questions.
   - **Questions:**
     - What is the highest rating in the dataset?
     - How many books have such a rating?
     - Which book has the most reviews? 
     - Which of the books from the Top 50 in 2015 is the most expensive (use an intermediate dataframe)? 
     - How many books of the Fiction genre were in the Top 50 in 2010 (use `&`)? 
     - How many books with a rating of 4.9 were in the rankings in 2010 and 2011 (use `|` or the `isin` function)?
2. Finally, sort ascending by price all books that were in the ranking in 2015 and cost less than 8 dollars (use the `sort_values` function).
   - **Question:** Which book is last on the sorted list?

## Data Aggregation and Table Joining

### Advanced Functions:
1. First, let's look at the maximum and minimum prices for each genre (use the `groupby` and `agg` functions along with `max` and `min` to calculate the minimum and maximum values). Do not select all columns, only those you need.
   - **Questions:**
      - Maximum price for the Fiction genre?
      - Minimum price for the Fiction genre?
      - Maximum price for the Non-Fiction genre?
      - Minimum price for the Non-Fiction genre?
2. Now create a new dataframe that will store the number of books for each author (use the `groupby` and `agg` functions, then use `count` to count the number). Choose only the necessary columns.
   - **Questions:**
      - What is the dimension of the table?
      - Which author has the most books?
      - How many books does this author have?
3. Create a second dataframe that will contain the average rating for each author (use the `groupby` and `agg` functions, then use `mean` to calculate the average). Choose only the necessary columns.
   - **Questions:**
      - Which author has the lowest average rating?
      - What is the average rating of this author?
4. Combine the last two dataframes to see the number of books and average rating for each author (use the `concat` function with axis=1). Save the result to a variable.
5. Sort the dataframes by ascending number of books and increasing rating (use the `sort_values` function).
   - **Question:** Which author is first on the list?


Submit the assignment as a Jupyter Notebook file named `Hw2.3.ipynb`.

## Visualization

For each of the previous assignments:
- `Hw2.1.ipynb`
- `Hw2.2.ipynb`
- `Hw2.3.ipynb`

Add 3 to 5 charts of various types. Make sure each chart in the homework differs from the others. You can use matplotlib or seaborn.

Do not forget to add `%matplotlib inline` directive to your Jupyter file to ensure charts are plotted within the document.
