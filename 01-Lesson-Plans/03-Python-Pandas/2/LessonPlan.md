## 3.2 Lesson Plan: Meet Pandas

### Overview

Today's class will introduce students to a powerful, open-source analytics library called Pandas, which is built into and runs on a Python environment. Pandas is a software library designed specifically for data analytics and time series analysis, which are useful features for quantitative analytics. In this lesson, students will learn how to use Pandas to create and manipulate DataFrames, locate data with indexing, clean data, create basic data visualizations, and conduct quantitative analysis to automate financial tasks. By the end of class, students should understand how Pandas is used to perform everyday financial analysis, including calculating daily returns over time.

### Class Objectives

By the end of class, students will be able to:

* Describe the benefits of Pandas over spreadsheets to manipulate data for financial use cases.

* Explain what a DataFrame is and how it differs from a series.

* Create DataFrames from CSV files and use basic commands to manipulate them.

* Clean data using built-in commands of DataFrames.

* Manipulate data using DataFrame indexes.

* Describe the basic theory and calculations of returns using Pandas.

* Create basic data visualizations with Pandas' built-in plotting functions.

### Instructor Notes

* Today’s lesson will introduce students to Pandas. Students may be confused as to why they are using Pandas now, having just learned Python. Help them understand the relationship between Python and Pandas, and why it makes sense at this point to transition to Pandas. Discuss Pandas from a Pythonic point of view, and emphasize that Pandas is written in Python. Underscore that Pandas is Python code that a user wrote for financial analytics–instead of hoarding their code in the depths of a hard drive, the creators packaged the functions and made them publicly available.

* The lesson starts with technical concepts, like reading in CSV files and checking for nulls, and progresses to more advanced skills, such as calculating daily and cumulative investment returns. Keep in mind that not all students have a finance background, and may not understand returns right away. Leverage the knowledge of finance-savvy students in the class and encourage them to help their partners if they get stuck. Be sure to allow enough time for students to ask questions at the end of each section.

* Keep in mind that some students may be confused by the concept of return on investment (ROI) but hesitant to vocalize their uncertainty. Encourage students to work in groups so that they can make sense of the activity and concepts together. TAs should circulate the classroom to assist groups, and you should make yourself available for financial or technical questions. Finally, consider asking the finance-savvy students to provide clarity and assistance for students who need help.

* The activities in this lesson focus on developing and honing skills that are critical for succeeding in this course, as well as performing daily tasks within the FinTech professional world. Therefore, encourage students to practice these skills outside of class to gain mastery.

* Have your TAs keep track of time with the [Time Tracker](TimeTracker.xlsx).

### Sample Class Video (Highly Recommended)


* To watch an example class lecture, go here: [3.2 Class Video.](https://codingbootcamp.hosted.panopto.com/Panopto/Pages/Viewer.aspx?id=b94c08e1-a82a-4800-a73c-aaa301156f9f) Note that this video may not reflect the most recent lesson plan.

### Class Slides and Time Tracker

* The slides for this lesson can be viewed on Google Drive here: [Lesson Slides](https://docs.google.com/presentation/d/116ZvNoFKLHkn1fAUI42lS-vV9BJ-UNAAdNRo2Ndu02Q/edit?usp=sharing).

* To add the slides to the student-facing repository, download the slides as a PDF by navigating to File, selecting "Download as," and then choosing "PDF document." Then, add the PDF file to your class repository along with other necessary files. You can view instructions for this [here](https://docs.google.com/document/d/1XM90c4s9XjwZHjdUlwEMcv2iXcO_yRGx5p2iLZ3BGNI/edit).

* **Note:** Editing access is not available for this document. If you wish to modify the slides, create a copy by navigating to File and selecting "Make a copy...".

* The Time Tracker for this lesson can be viewed here: [Time Tracker](TimeTracker.xlsx).

---

### 1. Instructor Do: Welcome Class and Introduction to Pandas (10 min)

In this section, you will give students a brief history of Pandas and an overview of its advantages, as well as explain why it's useful for FinTech professionals.

Welcome students to the first day of Pandas. Open the lesson slides and briefly review the class objectives.

Then, move to the "Hello Pandas!" section and highlight the following:

* Pandas is currently one of the most powerful libraries in Python for data manipulation and analysis. Because of this, it is one of the most important superpowers a FinTech professional can have. Instead of reinventing the wheel and writing your code, you will be able to leverage Pandas' repository of functions.

* Pandas was created by [Wes McKinney](https://wesmckinney.com/) to offer a flexible, high-performance tool for conducting quantitative analyses of financial data. Since 2008, Pandas has been used to manipulate, analyze, and visualize financial data.

* If Python was compared to a garage, Pandas would be the sleek Tesla parked inside. The owner could choose to leverage the speed, power, and efficiency of their Tesla and take it for a spin, or they could walk to their destination. While walking would produce the same result as using the Tesla, it would require extra labour and take more time. This lesson will teach you how to skillfully utilize the sleek Tesla sitting in your garage.

Continue to the "Why Pandas?" slides, and highlight the following:

* Since spreadsheets first appeared in [1969 when the plant budgeting operations of AT&T first used LANPAR](http://www.renepardo.com/), then again with [VisiCalc in 1970](https://en.wikipedia.org/wiki/VisiCalc) and again with [Microsoft Excel in 1987](https://en.wikipedia.org/wiki/Microsoft_Excel), they have transformed finance and quants analysis forever.

* However, as the volume and complexity of data has increased significantly, spreadsheets are now limited when it comes to data analysis.

Ask students what pain points they have experienced while using spreadsheets to handle data. Possible answers could include:

* Microsoft Office is expensive.

* Cell formulas can be challenging to edit.

* Spreadsheets can only hold so much data; the more data that is stored, the slower the workbook runs.

* Excel files often stop responding and are vulnerable to corruption.

* Automation and custom function creation is not inherent. Macros and VBA need to be learned.

Now ask students if they have experienced any disasters or significant challenges while working in Excel. Possible answers include:

* Excel hogged so much memory that my laptop crashed.

* Regional sales data for a sales competition was copied and pasted next to the wrong sales representatives. This resulted in the wrong person being identified as the winner.

* In a monthly budget spreadsheet, the Excel formula to calculate the remaining balance in a chequing account did not include the entire cell range necessary for the calculation; this resulted in the account having a negative balance.

After discussing some of the common pain points of spreadsheets, introduce Pandas and highlight the following:

* Fortunately, we have Pandas to help us manage data in Python.

* Pandas is one of the most powerful open source libraries in Python for analyzing and manipulating data.

* The library was born in 2008 at AQR Capital when Wes McKinney was looking for a high-performing, flexible tool to conduct quantitative analysis on financial data.

* Etymology: The name “Pandas” originates from “panel data structures.”

* Pandas doesn't require users to memorize formulas. Standard financial calculations and formulas are made available to Pandas users as functions.

* Pandas offers functions that ensure data is clean and ready for analytic use.

* Pandas functions range from simple arithmetic to complex statistics. This allows users to automate most, if not all, financial calculations. Instead of writing the formula in a cell or calculating by hand, users just need to make a function call (e.g., `pct_change` to calculate daily returns for an investment).

* Python + Pandas = the perfect combination for small experiments or for implementing large-scale production systems to analyze data and make smarter decisions.

* Pandas provides many advantages over spreadsheets due to its data structures and built-in functions for analysis.

  * Series (1D labelled vectors)
  * DataFrame (2D structures similar to spreadsheets)
  * Panel (Collection of DataFrames as 3D labelled arrays)

* Pandas offers built-in time series functionality, which is a must for financial and quants analysis.

Explain to students that they have already installed Pandas through Anaconda, so they don't need to install additional libraries. However, if they have issues running Pandas, they can use a free notebook by [Google Colaboratory](https://colab.research.google.com/) and troubleshoot their installation with a TA during a break or office hours.

Review the [instructions](../../../02-Homework/04-Pandas/Instructions/README.md) for the homework assignment. During this unit and the next, students will learn everything they need to know to complete this assignment. Focus on getting students excited about learning Pandas by previewing the skills and work they will accomplish by the end of the week. Emphasize calculating investment returns/profit over time, as well as plot visualizations.

If time allows, you can end by presenting the following Pandas applications which are discussed in more detail [here](https://data-flair.training/blogs/applications-of-pandas/) to give students a taste of what to expect in the field. Applications to highlight include:

* Stock prediction

* Analytics

* Data science

Slack out [this link](https://data-flair.training/blogs/applications-of-pandas/) to students so they can review the other applications outside of class.

Answer any questions before moving on.

---

### 2. Instructor Do: Reading CSV Files (10 min)

The goal of this part of the lesson is to get students comfortable with reading CSV files into Pandas. Financial data is commonly converted from other formats (e.g., a Microsoft Excel file) to CSV so that programs like Pandas can manipulate it. Learning how to read CSV data into Pandas is the first step in getting students started with creating automated analytics pipelines.

**Files:**

* [reading_csvs.ipynb](Activities/01-Ins_Reading_CSVs/Solved/reading_csvs.ipynb)

* [sales.csv](Activities/01-Ins_Reading_CSVs/Resources/sales.csv)

* [sales_no_header.csv](Activities/01-Ins_Reading_CSVs/Resources/sales_no_header.csv)

Open the lesson slides, move to "The Pandas DataFrame" section and highlight the following:

* A DataFrame is a particular data structure in Pandas that is designed to work with tabular data (data that has rows and columns like a spreadsheet) and provides some useful functions to help analyze and manipulate tabular data.

* A Pandas DataFrame can be created in several ways, such as using a Python dictionary, a list of lists, or reading data from an external file like CSV or JSON.

* The [Pandas DataFrame Documentation](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.html) and the [Pandas Getting Started Guide](https://pandas.pydata.org/docs/getting_started/intro_tutorials/01_table_oriented.html) are great resources if you want to learn more about creating DataFrames.

* Comma-separated values (CSV) is one of the most common file formats used to share data on finance. You will start working with DataFrames by creating them from CSV files.

Slack out to students the [Pandas DataFrame Documentation](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.html) and the [Pandas Getting Started Guide](https://pandas.pydata.org/docs/getting_started/intro_tutorials/01_table_oriented.html) and encourage them to review these resources at their own pace.

Continue by opening the two CSV files in the "Resources" directory (`sales.csv` and `sales_no_header.csv`) in VSCode or any other plain text editor to show students the format of the data. Point out that one file has a header, while the other does not. Refer back to these files during the demo as needed.

Next, open `reading_csvs.ipynb` Jupyter notebook and walk through the following aspects of the code with your students. Highlight the following in sequential order.

First, emphasize how to import Pandas.

* To use Pandas, the `pandas` library must be imported. Pandas is commonly aliased as `pd` at this time.

* The `Path` class is also imported from the [`pathlib` module](https://docs.python.org/3/library/pathlib.html) to deal with file paths across all operating systems without complexity.

  ```python
  import pandas as pd
  from pathlib import Path
  ```

* Next, we use the `Path` class to set the file path to the CSV file we want to load into a DataFrame.

  ```python
  csvpath = Path("../Resources/sales.csv")
  ```

Next, discuss the `read_csv` function.

* The `read_csv` function allows users to read a CSV file into a DataFrame.

* The function usually just needs the path to the file, which in this case is defined using the `Path` class.

  ```python
  sales_dataframe = pd.read_csv(csvpath)
  ```

Then highlight the `head` function.

* The `head` function shows the first five rows of the data by default.

* `head` is a common function used to take a peek at the DataFrame to ensure everything loaded correctly.

  ![dataframe.png](Images/dataframe.png)

Tell students that this data is a fake dataset about sales.

Continue the demo and explain to students that sometimes they may have situations where a given CSV file has no headers. Ask the the class the following question:

* How might the `read_csv` function deal with a CSV without a header?

  * **Possible Answer:** The `read_csv` function will automatically detect that there is no header and will raise an error.

  * **Possible Answer:** It's impossible to read a CSV file without headers in a DataFrame.

  * **Possible Answer:** Since there is no header, the `read_csv` function will take the first row as the file header.

Explain to students that if they load CSV files without a header into a DataFrame by passing just the file path to the `read_csv` function, the first row will be taken as the header.

Continue the demo by loading the `sales_no_header` file into a DataFrame, then use the `head` method to demonstrate to students the default behaviour for the `read_csv` function.

![Loading a CSV file with no header](Images/csv_no_header.png)

Now call attention to the `header` parameter for `read_csv` and highlight the following:

* The `header=None` parameter tells Pandas not to use the first row as the header. Because no header is specified, the column index numbers are used instead.

  ![header-none.png](Images/header-none.png)

* New headers can be supplied by assigning a new list of column names to the `columns` attribute.

  ![header-columns.png](Images/header-columns.png)

* It is common to generate high-level statistics when creating a DataFrame. In this case, the Pandas `describe` function can be used.

  ![describe_summary.png](Images/describe_summary.png)

* The output of the `describe` function is summary statistics for numeric fields, including series counts, averages, minimum value, maximum value, and so on.

* A limitation of the `describe` function is that it only calculates summary statistics for numeric values columns.

Consult the Pandas documentation to read more about the [read_csv](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.read_csv.html) function. Show the many options available in the function signature.

Explain that while the most common scenario is to provide the path to the file directly, Pandas provides a lot of configuration options for almost any other situation that may arise when reading CSV files, such as the parameters associated with the file path and header that were used in the demo code.

Congratulate the class on reading their first CSV file into Pandas! This is an exciting moment because students can now harness the power of Pandas to work with tabular data. Ask if there are any questions before moving on.

---

### 3. Student Do: Reading Stock Data from a CSV File (10 min)

In this activity, students will get hands-on experience reading CSV files into Pandas. They will use the `read_csv` function, sample data with the `head` function, and create DataFrames with specified column names.

**Files:**

* [reading_stock_data.ipynb](Activities/02-Stu_Reading_CSVs/Unsolved/reading_stock_data.ipynb)

* [shopify_stock_data.csv](Activities/02-Stu_Reading_CSVs/Resources/shopify_stock_data.csv)

**Instructions:**

* [README.md](Activities/02-Stu_Reading_CSVs/README.md)

---

### 4. Instructor Do: Review Reading Stock Data from a CSV File (5 min)

In this section, review the previous activity with students.

**Files:**

* [reading_stock_data.ipynb](Activities/02-Stu_Reading_CSVs/Solved/reading_stock_data.ipynb)

* [shopify_stock_data.csv](Activities/02-Stu_Reading_CSVs/Resources/shopify_stock_data.csv)

Open the solution file and review the following:

* To use Pandas, the `pandas` library must be imported into the Python environment.

  ```python
  import pandas as pd
  from pathlib import Path
  ```

* A DataFrame can be created from a CSV file with the `read_csv` function. This example uses a `Path` object to specify the location of the CSV file. Pandas can then read that file and create a DataFrame to hold the data.

  ```python
  # set the file path
  file_path = Path("../Resources/shopify_stock_data.csv")

  # create a Pandas DataFrame from a csv file
  df = pd.read_csv(file_path)
  ```

* The `head` function can be used to output the first `n` number of lines from a DataFrame. It is common for a sample of a DataFrame to be output to make sure that headers and rows were imported correctly.

  ![First record as columns names](Images/05_first_record_as_columns_names.png)

* The `header=None` parameter can be specified to prevent the first row of data from being used as column names when there is no header provided. Once the `header` is set to `None`, the `df.columns` function can be used to assign column names.

  ![Setting new columns names](Images/05_set_columns_names.png)

Ask if there are any questions before moving on.

---

### 5. Instructor Do: Column Manipulation (10 min)

In this part of the lesson, students will learn how to use various Pandas functions to manipulate columns. Students must know how to create and curate DataFrames to fit their needs.

**Files:**

* [column_manipulation.ipynb](Activities/03-Ins_Columns/Solved/column_manipulation.ipynb)

* [customers.csv](Activities/03-Ins_Columns/Resources/customers.csv)

Transition to the topic of column manipulation by covering the following talking points:

* Reading CSV data into Pandas is an easy feat, but sometimes the DataFrame's schema/structure needs to change. This includes changing DataFrame column names, adding columns, and dropping columns.

* Now it's time to learn how to use the various Pandas functions to perform each of these operations. You need to know how to create and curate DataFrames to fit your needs.

* In the previous activity, you created a Pandas DataFrame from a CSV file and assigned column names to the DataFrame. This was one example of column manipulation. There are also other ways to manipulate columns, and this demonstration will cover some of the most common techniques.

Open the solution file and demonstrate the fundamentals of column manipulation in Pandas:

* Pandas DataFrames have a `columns` attribute that shows the current column names.

  ![column-names.png](Images/column-names.png)

* The `columns` attribute can be assigned a new list of column values. This has certain restrictions, such as requiring the length of the new list of column names to match the number of columns in the DataFrame (no partial lists). This is valuable whenever column names need to be changed.

  ![replace-columns.png](Images/replace-columns.png)

* The `rename` function can be used to replace or update column names selectively. Simply provide a dictionary to the column's parameter that has the following format:

  ```python
  {
    "Old Column Name": "New Column Name"
  }
  ```

  ![rename-columns.png](Images/rename-columns.png)

* Columns can also be reordered by supplying a list of columns in the desired order.

  ![reorder-columns.png](Images/reorder-columns.png)

* New columns can be created by assigning a Pandas series to a new column name. This is similar to how dictionaries add values for new keys.

  ![create-columns.png](Images/create-columns.png)

* Sometimes, columns may need to be split into separate values. Pandas allows you to split a column based on a delimiter. In this case, the values are split by the whitespace between the names. The `expand=True` flag tells Pandas to create two new columns from the split. These columns can be assigned to new column names in the DataFrame.

  ![split-columns.png](Images/split-columns.png)

* Finally, columns that are no longer needed can be dropped using the `drop` function. Simply supply a list of the columns that should be dropped from the DataFrame.

  ```python
  # Use the `drop` method to delete a column from the `customer_dataframe`
  customer_dataframe = customer_dataframe.drop(columns=["full_name"])
  ```

Slack out the solution file to students to use as a reference. Now that students have created, split, renamed, and dropped columns, they can move onto the next step of data wrangling: data cleaning.

---

### 6. Instructor Do: Data Cleaning (10 min)

Students will now take part in a lecture and discussion about data cleaning. They will learn what data cleaning is, why it is necessary, and common strategies for cleaning data. This part of the lesson is crucial, as most of the data encountered in the real world is "dirty" and unusable.

**Files:**

* [data_cleaning.ipynb](Activities/04-Ins_Data_Cleaning/Solved/data_cleaning.ipynb)

* [order_data.csv](Activities/04-Ins_Data_Cleaning/Resources/order_data.csv)

Open the lesson slides, move to the "Data Cleaning" section, and highlight the following:

* Up to this point, you have been working with clean data already curated for use. But in the real world, data is messy and needs to be prepared for it to be valuable. This process is called **data cleaning**.

* Data cleaning consists of three parts:

  1. Data exploration

  2. Data quality checks

  3. Data cleaning strategies

Explain to students that you will demonstrate each of these parts, so that they can confidently clean and prep data for analysis.

Introduce data cleaning by covering these points:

* Data cleaning is critical to financial analytics. Data quality issues comprise the integrity or "health" of a dataset, which, in turn, creates a need for data cleaning.

* The goal of data cleaning is to keep the "plumbing" of data pipelines clean and in working condition so that analytics can run smoothly.

Discuss how data quality is determined.

* Most data quality rules are influenced by general coding etiquette (e.g., using correct data types, minimizing the use of nulls) as well as general data requirements (e.g., strings are characters and numerics are numbers).

* However, many companies create their own data governance rules and policies that dictate what makes each data element complete, consistent, valid, and accurate.

* The rules that govern data cleaning are defined by industry-accepted standards/best practices and various data storage design theories. For example:

  * Numerical fields should not contain string characters, only digits.

  * There should not be any duplicate rows in a dataset.

* Data quality rules are also defined by business or functional rules. Sometimes data needs to be stored or formatted in a unique way for business needs. For example, an international company might store dates as `DD/MM/YYYY`, whereas an American company might store dates as `MM/DD/YYYY`.

Mention to students that these rules can all be researched outside of class.

Ask students to propose some reasons why data might become dirty. Then, highlight some of the common reasons for having dirty data:

* **Typos:** When manually entering data, users can enter typos. If gone unchecked, typos can corrupt data values. There is little that can be be done to get rid of typos, as it is often difficult to identify them.

* **Human error:** Humans can copy and manipulate data incorrectly. For instance, someone might copy and paste data into the wrong Excel file, or a Python function can incorrectly compute a data value. If these issues are not fixed, data quality issues will arise down the road.

* **Poor data management:** Data is poorly managed when it is not cleaned or stored in an effective way. While not all data needs to be cleaned, industry standards and business rules should be consistently implemented to ensure the integrity of data.

Discuss approaches for identifying data quality issues while you switch to Jupyter lab to live code a few examples.

* The first step in assessing data for quality issues is to evaluate a sample of the data visually. This allows programmers to identify obvious quality issues as well as any skewed rows (e.g., a customer address in a first name field).

* To load the CSV file into the DataFrame, we set the parameter `index_col="order_no` to use the `order_no` columns as index instead of the default numerical index that Pandas generates.

* To get a sample of the data, Pandas provides the `sample` function to randomly select rows from a DataFrame. We will fetch five rows in this demo.

  ![LP_Ins_Data_Cleansing_Sample_Data.PNG](Images/LP_Ins_Data_Cleansing_Sample_Data.PNG)

* The `dtypes` function can be used to return the data type of each Series/column.

    **Note:** It's crucial to review data types after loading data into a DataFrame, as Pandas automatically assigns a data type to a Series. There are instances where Pandas is unable to infer the data type. Students will need to be aware of when this happens, so that they can assign the proper data type.

  ![LP_Ins_Data_Cleansing_Data_Types.PNG](Images/LP_Ins_Data_Cleansing_Data_Types.PNG)

* Record counts should always be reviewed, to ensure the expected number of rows matches the actual number.

* The total number of records can be identified using the `count` function. The `count` function counts the number of non-null cells for each column or row in a Pandas DataFrame.

  ![LP_Ins_Data_Cleansing_Count.PNG](Images/LP_Ins_Data_Cleansing_Count.PNG)

At this point, ask students:

* Why do you think there are unequal counts in the data?

  * **Answer:** Because there are nulls and missing data.

* Similarly, the quality of data can be assessed by using the `value_counts` function, which is a function that identifies the number of times a value occurs in a Series or column.

* `value_counts` reveals how many times a value occurs in a Series, with the most occurring value first.

    ![LP_Ins_Data_Cleansing_Distinct_Customer.PNG](Images/LP_Ins_Data_Cleansing_Distinct_Customer.PNG)

* Identifying `nulls` is key in assessing data quality health.

* Pandas offers a native function, `isnull()`, that can be used to identify missing values in a field represented as Python `None` objects.

* The `isnull()` function identifies which column values are nulls and which ones are not.

* If a column value is null, `isnull()` returns `True`. If the value is not null, `isnull` returns `False`.

  ![LP_Ins_Data_Cleansing_CSV_Isnull.png](Images/LP_Ins_Data_Cleansing_CSV_Isnull.png)

* Assessing the percentage of nulls for the entire DataFrame is also valuable, especially when it comes to determining what should be done with the nulls in a DataFrame.

* The percentage of nulls will influence the course of action for cleaning nulls, namely, dropping the nulls or leaving them alone.

  ![LP_Ins_Data_Cleansing_Null_Pct_Check.PNG](Images/LP_Ins_Data_Cleansing_Null_Pct_Check.PNG)

* Another method for determining how many nulls are in the DataFrame is to calculate the sum of all nulls.

  ![LP_Ins_Data_Cleansing_No_Of_Null.PNG](Images/LP_Ins_Data_Cleansing_No_Of_Null.PNG)

* Nulls can be cleaned by replacing them with a default value: "Unknown", 0, or mean(). This is exactly what Pandas' `fillna` does!

* `Fillna` will replace every instance of `null` with the provided default value. For this reason, the function should be executed against a Series.

  ![LP_Ins_Data_Cleansing_Fill_Na.png](Images/LP_Ins_Data_Cleansing_Fill_Na.png)

* Once nulls have been identified through a data quality process, a decision can be made to either drop the nulls or leave them.

* The `dropna` Pandas function can be used to drop all null values.

* Since we are creating a brand new DataFrame based on the original data but without null values, it's a good practice to use the `copy` function as well.

  ![Dropping all rows with null values](Images/df-dropna.png)

* A best practice is to combine the `isnull` function with the `sum` function to test the `dropna` function; this serves as a unit test of the `dropna` function. The expectation is there should be a count of 0 nulls for each Series.

  ![LP_Ins_Data_Cleansing_No_Of_Null_2.PNG](Images/LP_Ins_Data_Cleansing_No_Of_Null_2.PNG)

* Pandas also offers the `duplicated` function to identify duplicate rows in a DataFrame. Duplicate rows are essential to check because they can result in increased wait times for processing. Duplicate rows will also skew data aggregations, inflating aggregated numbers.

* The `duplicated` function returns either `True` or `False`.

  ![LP_Ins_Data_Cleansing_Duplicated_Check.PNG](Images/LP_Ins_Data_Cleansing_Duplicated_Check.PNG)

* The `drop_duplicates` function cleans duplicate rows. This function can be executed against a DataFrame or a Series. We are using the `copy` function to create a brand new DataFrame without duplicates.

  ```python
  # Clean duplicates
  csv_data = csv_data.drop_duplicates().copy()
  ```

Next, tell students you will live code a few data quality checks that are especially relevant for financial data. Cover the following points in your discussion:

* FinTech is all about manipulating financial data. Being able to inspect numeric values and gauge the quality of numerical data is critical to student success when analyzing and aggregating data.

* A quick and easy way to confirm the quality of a numeric value is to sample the data and do a spot check.

  ![LP_Stu_Data_Cleansing_Head_Currency.PNG](Images/LP_Stu_Data_Cleansing_Head_Currency.PNG)

* Because the `order_total` field has currency symbols in the values, numeric operations cannot be performed. A custom cleaning operation will need to be created in order to remove these symbols from the dataset.

* The cleaning operation can be created by leveraging and combining other Pandas functions (e.g., the Pandas `replace` function).

  ![LP_Ins_Data_Cleansing_Currency_Clean.png](Images/LP_Ins_Data_Cleansing_Currency_Clean.png)

* Once the currency symbols have been removed from the numeric field, the field can be converted to the appropriate data type.

  ![LP_Ins_Data_Cleansing_AsType.PNG](Images/LP_Ins_Data_Cleansing_AsType.PNG)

Ask if there are any questions before moving on.

---

### 7. Student Do: Spring Cleaning (15 min)

In this activity, students will perform a series of data quality checks on stock data to ensure the data is ready for analytical use. The objective of this activity is for students to learn how to clean data using Pandas native functions: `count`, `isnull`,`sum`,`mean`,`fillna`, and `replace`.

**Files:**

* [spring_cleaning.ipynb](Activities/05-Stu_Data_Cleaning/Unsolved/spring_cleaning.ipynb)

* [stock_data.csv](Activities/05-Stu_Data_Cleaning/Resources/stock_data.csv)

**Instructions:**

* [README.md](Activities/05-Stu_Data_Cleaning/README.md)

---

### 8. Instructor Do: Review Spring Cleaning (5 min)

In this part of the lesson, review the solution to the data cleaning activity with students.

**Files:**

* [spring_cleaning.ipynb](Activities/05-Stu_Data_Cleaning/Solved/spring_cleaning.ipynb)

* [stock_data.csv](Activities/05-Stu_Data_Cleaning/Resources/stock_data.csv)

Review data cleaning from a conceptual standpoint, mentioning the following points to students:

* Data cleaning is important because it removes all of the issues and errors that would block or inhibit computation.

* Without data cleaning, financial data can be calculated and aggregated incorrectly and inaccurately. Data quality issues can skew financial numbers, with inaccurate numbers being reported. Since numbers drive business decisions in the financial world, the use of incorrect data can have catastrophic implications.

Open the solution file, review the activity solution, and highlight the following:

* The `shape` function provides a quick and easy way to understand the structure of a DataFrame, including the number of columns and number of tuples/rows in the DataFrame.

  ```python
  csv_data.shape
  ```

  ```text
  (504, 14)
  ```

* Performing a `count` is a great way to assess how many records were loaded into a DataFrame for each Series. The output of `count` reflects the total number of non-null values.

  ```python
  csv_data.count()
  ```

  ```text
  symbol                504
  name                  502
  sector                501
  price                 500
  price_per_earnings    497
  dividend_yield        499
  earnings_per_share    498
  52_week_low           500
  52_week_high          500
  market_cap            500
  ebitda                492
  price_per_sales       500
  price_per_book        492
  sec_filings           500
  dtype: int64
  ```

Ask students the following question:

* What steps should be taken if all values in a Series are null?

  * **Answer:** The Series should be dropped.

* Nulls can throw a wrench in an analytic pipeline. The `isnull` function will identify which Series has nulls. If there are nulls, they can be removed or filled. The `dropna` and `fillna` functions provide this functionality, respectively. Note that it's important to understand which fields can have nulls and which cannot.

* Using `mean` with `isnull` will calculate the percentage of nulls for a DataFrame. This is important when considering the distribution of missing values in a DataFrame. The percentage of nulls can impact how the missing values are cleaned.

  ```python
  csv_data.isnull().mean() * 100
  ```

  ```text
  symbol                0.000000
  name                  0.396825
  sector                0.595238
  price                 0.793651
  price_per_earnings    1.388889
  dividend_yield        0.992063
  earnings_per_share    1.190476
  52_week_low           0.793651
  52_week_high          0.793651
  market_cap            0.793651
  ebitda                2.380952
  price_per_sales       0.793651
  price_per_book        2.380952
  sec_filings           0.793651
  dtype: float64
  ```

* The records with null values are dropped, and a new DataFrame is created.

  ```python
  csv_data = csv_data.dropna().copy()
  ```

* It's a common practice to double-check for nulls, so the `isnull` function is used together with the `sum` function to verify if there are any null values.

  ```python
  csv_data.isnull().sum()
  ```

  ```text
  symbol                0
  name                  0
  sector                0
  price                 0
  price_per_earnings    0
  dividend_yield        0
  earnings_per_share    0
  52_week_low           0
  52_week_high          0
  market_cap            0
  ebitda                0
  price_per_sales       0
  price_per_book        0
  sec_filings           0
  dtype: int64
  ```

* To set the default value for the `ebita` column to `0`, we use the `fillna` function.

  ```python
  csv_data["ebitda"] = csv_data["ebitda"].fillna(0)
  ```

* Finally, to remove duplicate values, the `drop_duplicates` function is used together with the `copy` function to create a newly cleaned DataFrame.

  ```python
  csv_data = csv_data.drop_duplicates().copy()
  ```

Continue by showing the solution for the "Challenge" and highlight the following:

* We start the challenge section by taking a quick sample of the data using the `head` function.

  ```python
  csv_data["price"].head()
  ```

  ```text
  0    $222.89
  2      56.27
  3     108.48
  5     108.48
  6     185.16
  Name: price, dtype: object
  ```

* As you note, the `price` column has `$` currency symbols that need to be removed.

* We remove the `$` currency symbols using the `str` and the `replace` functions.

  ```python
  csv_data["price"] = csv_data["price"].str.replace("$", "")
  csv_data["price"].head(10)
  ```

  ```text
  0     222.89
  2      56.27
  3     108.48
  5     108.48
  6     185.16
  7     109.63
  10       178
  11    179.11
  14     152.8
  15     62.49
  ```

* Although we remove the `$` currency symbols, the data type of the `price` column is still object.

  ```python
  csv_data["price"].dtype
  ```

  ```text
  dtype('O')
  ```

* We end the challenge section by casting the `price` column to float.

  ```python
  csv_data["price"] = csv_data["price"].astype('float')
  csv_data["price"].dtype
  ```

  ```text
  dtype('float64')
  ```

For more comprehensive data cleaning strategies, slack out the following [link](https://www.kaggle.com/search?q=cleaning+data+with+python+in%3Anotebooks+authorUserName%3Achrisbow) for curious students who want to learn more about data-cleaning processes using Python. Ask if there are any questions before moving on.

---

### 9. Instructor Do: Indexing (10 min)

In this part of the lesson, students will learn how to locate and select data within a DataFrame through indexing.

**Files:**

* [indexing.ipynb](Activities/06-Ins_Indexing/Solved/indexing.ipynb)

* [people.csv](Activities/06-Ins_Indexing/Resources/people.csv)

Open the unsolved version of the Jupyter notebook and live code the activity, explaining the following:

* When you work with financial data, a common practice is to query your dataset to look for a particular record or to make adjustments on some values.

* The Pandas DataFrame has some functions to locate and select data using indexing.

* Indexing allows us to slice and dice our data so that we can get or set values for any of the cells in our table.

Explain to students that for this demo, you will use a fictional customer dataset. The demo starts by loading the dataset into a Pandas DataFrame.

![Loading customers data](Images/load-customer-data.png)

Continue the demo and highlight the following:

* After loading the customer's data into the DataFrame, we fetch the summary statistics of the numeric columns with the `describe` function.

![Fetching summary statistics from numerical columns](Images/customer-df-describe.png)

* If you want to fetch the descriptive statistics of all the columns, including the ones that are not numerical, you should pass the parameter `include="all"` to the `describe` function.

![Fetching summary statistics from all columns](Images/customer-df-describe-all.png)

Explain to students that now you will show them how they can slice and dice the data. Highlight the following:

* By default, the index of a DataFrame is numerical and starts at zero. The `iloc[]` function returns row data based on a numerical index.

  ![iloc-first-row](Images/iloc-first-row.png)

* The `iloc[]` function can return a range of rows based on a numerical index range.

  ![iloc-first-10](Images/iloc-first-10.png)

* The `iloc[]` function can return row data of specific columns.

  ![iloc-second-column](Images/iloc-second-column.png)

* The `iloc[]` function can return a combination of specific rows and columns.

  ![iloc-row-column-combo](Images/iloc-row-column-combo.png)

* The `iloc[]` function can be used to modify specific row values.

  ![iloc-assignment](Images/iloc-assignment.png)

* To use the `loc[]` function on the index of a DataFrame, string values need to be set as the index using the `set_index()` function. Note that `set_index` does not return a new DataFrame but instead creates a copy of the original. Any changes made to the indexed DataFrame will be passed on to the original DataFrame.

  ![index_overview](Images/index_overview.png)

* We can use the `sort_index` function to order the data alphabetically according to the new `first_name` index.

  ![Sort index demo](Images/customers-df-sort-index.png)

* The `loc[]` function returns a row based on a string index.

  ![loc-string](Images/loc-string.png)

* The `loc[]` function can return a range of rows based on a range of string indexes.

  ![loc-string-range](Images/loc-string-range.png)

* The `loc[]` function can return rows based on column value conditionals.

  ![loc-conditional](Images/loc-conditional.png)

* The `loc[]` function can modify specific row values.

  ![loc-assignment](Images/loc-assignment.png)

Finally, explain that it will take some time to get used to indexing data with Pandas; but over time, it will become second nature. Practice makes perfect!

Ask if there are any questions before moving on.

---

### 10. Student Do: Three-Year Loans (15 min)

Now that students have the conceptual knowledge to index and look up data, it's time they get some practice. In this activity, students will use DataFrame indexing on the dataset in `loans.csv` in order to generate insights about three-year loan customers.

Note that the data in `loans.csv` is a compilation of many different columns and loan durations. Students will need to filter the data and use functions on data subsets to answer the activity questions.

**Files:**

* [loans.ipynb](Activities/07-Stu_Indexing/Unsolved/loans.ipynb)

* [loans.csv](Activities/07-Stu_Indexing/Resources/loans.csv)

**Instructions:**

* [README.md](Activities/07-Stu_Indexing/README.md)

---

### 11. Instructor Do: Review Three-Year Loans (5 min)

Use this part of the lesson to review the previous activity with students.

**Files:**

* [loans.ipynb](Activities/07-Stu_Indexing/Solved/loans.ipynb)

* [loans.csv](Activities/07-Stu_Indexing/Resources/loans.csv)

Open the solution file and explain the following while doing a dry walkthrough:

* Displaying an index of the first 10 rows is similar to what the `head()` function does; however, utilizing `iloc[]` gives you more control over the index ranges.

  ![First 10 Records](Images/first-10-records.png)

* The `iloc[]` function allows for selecting the specific row and column indexes. In this case, the `:` keyword suggests that all rows will be returned from the `0`, `3`, `4`, `8`, `11`, and `16` column indexes. We can also use slicing with `iloc[]` to create a new DataFrame.

  ![Specific Columns](Images/specific-columns.png)

* We fetch the summary statistics of all the columns setting the parameter `include="all"` in the describe function.

  ```python
  loans_csv.describe(include="all")
  ```

* The `loc[]` function combines conditionals with column-value reassignment to modify specific values within a DataFrame.

  ![row-modification-without-warning](Images/row-modification-without-warning.png)

* To get the summary statistics of the 3-year term loans, we use the `describe` function by setting the parameter `include="all"`.

  ```python
  term_df.describe(include="all")
  ```

* The `value_counts()` function counts the frequency of unique values of a specific column or Series object.

  ![Unique Values](Images/unique-values.png)

* To get the summary statistics for 3-year loans of customers with an annual income greater than $80,000 or less than $80,000 we filter the DataFrame using `loc` and conditionals.

  ![Filtering Loans](Images/filtering-loans.png)

Ask if there are any questions before moving on.

---

### 12. BREAK (15 min)

---

### 13. Instructor Do: Pandas Visualizations (10 min)

This part of the lesson is focused on creating charts using Pandas visualization functions. You will demo how to plot data with and without indexes, as well as use line and bar charts.

**Files:**

* [visualization.ipynb](Activities/08-Ins_Pandas_Visualization/Solved/visualization.ipynb)

* [annual_gold.csv](Activities/08-Ins_Pandas_Visualization/Resources/annual_gold.csv)

Open the unsolved version, live code the demo and explain the following:

* Pandas makes visualization easy by including a DataFrame `plot()` function. The `plot()` function uses data from a DataFrame to set x- and y-axis data points.

* The `plot()` function uses `matplotlib`, a Python data visualization library, to create the plots.

* To display the plots in the notebook's canvas, you need to set [Jupyter notebook's magic command](https://ipython.readthedocs.io/en/stable/interactive/magics.html) with the name `matplotlib`. A magic command allows us to add interactive elements to a Jupyter notebook, like plots.

* To introduce a magic command, you should start with the percentage symbol `%` followed by the command name and, optionally, a parameter. In this demo, we pass the `inline` parameter to the `matplotlib` magic command to allow the plots to be displayed in the notebook's canvas.

  ```python
  %matplotlib inline
  ```

* Plotting data without defining the index will only display the default index of each row in the DataFrame. To set the dates as the x-axis label, the `Date` column needs to be set as the index.

  ![line-chart-without-index](Images/line-chart-without-index.png)

* While setting the `Date` column as the DataFrame index, it's a good practice to convert date strings into DateTime objects; this allows for the use of additional DateTime functionality.

  ![set-index](Images/set-index.png)

* Be sure to drop the extra `Date` column after setting it as the index.

  ![drop-column](Images/drop-column.png)

* Plotting data with datetimes as the index allows us to see the dates as the x-axis label of the line chart.

  ![line-chart-with-index](Images/line-chart-with-index.png)

* Use the `kind` parameter with the `plot()` function to specify different types of charts. The `plot()` function automatically defaults to generating a line chart.

  ![bar-chart](Images/bar-chart.png)

* Use the `figsize` parameter with the `plot()` function to increase or decrease the chart size. This is especially helpful when there are many x- or y-axis data points.

  ![bar-chart-large](Images/bar-chart-large.png)

Slack out to students the [Pandas Visualization help document](https://pandas.pydata.org/pandas-docs/stable/user_guide/visualization.html) as a further reference to the different kinds of plots Pandas includes. Ask if there are any questions before moving on.

---

### 14. Student Do: Market Analysis (15 min)

In this activity, students will use Pandas to create three different charts: pie chart, bar chart, and scatter plot. This activity will teach students how to create pie charts and scatter plots in addition to bar and line plots.

Circulate the classroom to review student progress as they complete the activity. Guidance may be required, as this is the first time students will be exposed to pie charts and scatter plots.

**Files:**

* [market_analysis.ipynb](Activities/09-Stu_Pandas_Visualization/Unsolved/market_analysis.ipynb)

* [sp500_companies.csv](Activities/09-Stu_Pandas_Visualization/Resources/sp500_companies.csv)

**Instructions:**

* [README.md](Activities/09-Stu_Pandas_Visualization/README.md)

---

### 15. Instructor Do: Review Market Analysis (5 min)

In this section, review the previous activity with students.

**Files:**

* [market_analysis.ipynb](Activities/09-Stu_Pandas_Visualization/Solved/market_analysis.ipynb)

* [sp500_companies.csv](Activities/09-Stu_Pandas_Visualization/Resources/sp500_companies.csv)

Open the solution file and explain the following:

* Setting the `%matplotlib inline` feature is necessary for displaying the plots in the Jupyter Notebook file.

  ```python
  # Import libraries and dependencies
  import pandas as pd
  from pathlib import Path
  %matplotlib inline
  ```

* The `value_counts()` function returns a Series object that represents the frequency of unique values of a Series object or column of a DataFrame.

  ![value-counts-function](Images/value-counts-function.png)

* The `plot` function defaults to line charts; however, the `kind` parameter allows you to alter the type of chart produced (e.g., pie chart, bar chart).

  ```python
  # Plot a pie chart from the distribution of company sectors
  sector_count.plot(kind="pie")
  ```

* A pie chart is best suited for representing the distribution of an entire category, which, in this case, is the distribution of company sectors in the S&P 500. The plot shows that consumer discretionary companies hold the most significant weight or proportion among the S&P 500 companies.

  ![pie_chart](Images/pie.png)

* To create certain plots, it may be easier to create a subset of the original DataFrame. In this example, the `Symbol` and `Market Cap` columns can be selected as a subset of the original data.

  ```python
  market_cap = sp500_companies_csv.loc[:, ["Symbol", "Market Cap"]]
  ```

* When plotting a DataFrame, set the index to a specific column to ensure the desired chart labels are displayed (for example, the x-axis labels on a line or bar chart).

* Use the `nlargest()` function to return the top `n` number of rows based on a particular DataFrame column.

  ![nlargest-function](Images/nlargest-function.png)

* A bar chart is best suited for comparing the values of several variables of the same type, which in this case are the market caps of the top 20 companies in the S&P 500. The plot shows the varying market cap values of the top 20 market cap companies in the S&P 500.

  ![bar_chart](Images/bar.png)

* A scatter plot is best suited for comparing the relationship between two variables, which in this case is the relationship between price and earnings. The plot shows that there is a common range in which most companies tend to cluster in regards to price and earnings. However, as earnings increase, there seems to be a slight positive trend in price as well.

  ![scatter_plot](Images/scatter.png)

Ask if there are any questions before moving on.

---

### 16. Instructor Do: Returns (10 min)

The following demo introduces students to calculating daily returns with Pandas. It will also cover the return on investment (ROI), the `pct_change` function, and cumulative returns. This section will build upon skills students have already learned: reading in CSV data, manipulating and cleaning DataFrames, and plotting data.

**Files:**

* [returns.ipynb](Activities/10-Ins_Returns/Unsolved/returns.ipynb)

* [TSX_Data.csv](Activities/10-Ins_Returns/Resources/TSX_Data.csv)


Open the lesson slides and move to the "Returns" section, introduce the concept of ROI, and highlight the following:

* A **return on investment (ROI)** is a percentage calculation that signifies either a profit or loss relative to the initial cost of an investment.

* ROI calculations can be used to standardize and compare the investment performances of varying asset classes, such as equities, bonds, real estate, etc.

* **Daily returns** are a series of returns calculated over several days, with each daily return representing the relative increase or decrease in investment between days.

* **Cumulative returns** are a series of returns in which each return represents the relative increase or decrease in the price of an asset at the time `t`, compared to the initial price of that asset at the time `t0`. Cumulative returns describe the progression of the return on investment of an asset over time.

Explain to students that ROI, daily returns and cumulative returns can all be easily calculated in pure Python. Show them the code in the slide for calculating ROI, then switch to the unsolved version of the Jupyter notebook to begin the demo.

Incorporate the following points into your demonstration as you live code the solution:

* Let's imagine that you invested $100 last week in a single stock.

* Suppose that you check the current price of the stock today and its current price is $110.

* How can you calculate the ROI using Python?

  ```python
  # ROI = (Current Value of Investment - Cost of Investment) / Cost of Investment
  initial_investment = 100
  current_price = 110

  roi = (current_price - initial_investment) / initial_investment
  roi_pct = roi * 100
  print(f"ROI for an initial investment of ${initial_investment}"
        f"now priced at ${current_price}"
        f"is {roi} or {roi_pct}%")
  ```

  ```text
  ROI for an initial investment of $100 now priced at $110 is 0.1 or 10.0%
  ```

* After calculating the ROI, you can see it's `0.1` or `10%`.

Continue the demo and explain to students that you will now cover calculating daily and cumulative returns using sample data from the [S&P/TSX Composite Index](https://en.wikipedia.org/wiki/S%26P/TSX_Composite_Index).

Conduct a dry walkthrough of the code that loads the S&P TSX data and prepares the DataFrame to start the analysis. After plotting the daily close price, continue the demo and highlight the following:

* When calculating *daily returns* we can use the `shift` function.  This function creates an offset of a DataFrame index by a specified amount. In this case, the index of the `tsx_csv` is offset by `1` to emulate the daily return formula.

  ![shift-function](Images/shift-function.png)

* Alternatively, the `pct_change()` function can be used.  This function calculates the percentage difference between each element of a time series. Therefore, for time series data such as daily closing prices of a stock, using the `pct_change()` function conveniently produces a series of daily returns.

  ![pct-change-function](Images/pct-change-function.png)

* Plotting daily returns makes it easier to see overall variations in daily returns over time. In particular, plotting daily returns makes it easier to see high and low spikes compared to the general trend. Such spikes in daily returns may indicate a market event.

  ![Plot of Daily Returns](Images/daily-return-plot.png)

* To calculate *cumulative returns, we can use the `cumprod()` function.  This function multiplies each number in a series with the next successive number until the end of the series.

* In the equation `(1 + daily_returns).cumprod()`:

  * Each daily return is expressed as a capital multiplier (e.g., daily return of 0.5% is 1.005).

  * The `cumprod()` function cumulatively multiplies each number with its successive number.

  * Sometimes, the form `(1 + daily_returns).cumprod() - 1` is used; the `-1` brings the result from a capital multiplier expression back to a typical return value scale (e.g., daily return of 0.5% is 0.005).

  ![cumprod-function](Images/cumprod-function.png)

* Plotting cumulative returns makes it easier to visualize the profitability of a single asset and, in particular, the profitabilities of several asset classes over time. In this case, the plot shows that the S&P TSX lost a good deal of its value in 2015, but began a recovery tendency in 2016.

  ![Plot of Cumulative Returns](Images/cumulative-return-plot.png)

Now that students know how to calculate and plot returns, they will practice doing these skills by analyzing and plotting historical Shopify data for Harold.

Answer any questions before moving on.

---

### 17. Student Do: Returns Over Date Ranges (15 min)

In this activity, students will analyze historical price data for Shopify and plot the daily returns over the previous 1-, 2-, 3-, and 4-year periods. They will also need to find and show the differences in average daily returns for each period to determine whether a short or long-term perspective should be used in prospecting Shopify as a potential investment opportunity.

**File:**

* [returns_over_date_ranges.ipynb](Activities/11-Stu_Returns/Unsolved/returns_over_date_ranges.ipynb)

* [shopify_stock_data.csv](Activities/11-Stu_Returns/Resources/shopify_stock_data.csv)

**Instructions:**

* [README.md](Activities/11-Stu_Returns/README.md)

---

### 18. Instructor Do: Review Returns Over Date Ranges (5 min)

In this section, review the solution to the previous activity with students.

**Files:**

* [returns_over_date_ranges.ipynb](Activities/11-Stu_Returns/Solved/returns_over_date_ranges.ipynb)

* [shopify_stock_data.csv](Activities/11-Stu_Returns/Resources/shopify_stock_data.csv)

Tell students to turn to the person sitting next to them and spend the next three minutes doing the following:

* Share two new things they learned about returns.

* Share answers to the following questions:

  * What is the value of calculating cumulative returns?

  * Why not just calculate daily returns over time?

With the remaining time, open the solution file and discuss the following points:

* Set the `%matplotlib inline` feature to display plots in Jupyter Notebook.

  ```python
  # Import libraries and dependencies
  import pandas as pd
  from pathlib import Path

  %matplotlib inline
  ```

* Read in the CSV as a DataFrame and do a quick analysis of summary statistics. Then trim the data to match the needs of the requirements. In this case, only the Close column is needed to calculate daily returns.

  ![drop-columns](Images/drop-columns.png)

* Set the date as the index to slice the DataFrame by specified date ranges using the `loc` function; this allows for `[start:end]` notation.

  ![datetime-index](Images/datetime-index.png)

* Notice the hard coding required to create the slice notations for each period. It would be more convenient to be able to choose a date and use a function to go 365 days before that date to create 1-year, 2-year, 3-year, and 4-year time chunks; `datetime` objects will help us do this in the future.

  ```python
  # Slice DataFrame into 1 year timeframe
  daily_return_1_year = daily_return.loc["2018-12-30":"2019-12-31"]
  daily_return_1_year
  ```

* The data shows that trading Shopify in the short term is potentially more profitable, as the average daily return of a 1-year time frame is the highest at `0.004532`, or `4.53%`.

Get students to briefly reflect on what they've just learned by asking the following question:

For what other accounts can daily returns be used to determine the return on investment?

**Answer:** Savings accounts and Registered Retirement Savings Plan (RRSP) accounts generate daily ROI.

Ask if there are any questions before moving on.

---

### End Class

---

© 2020 Trilogy Education Services, a 2U, Inc. brand. All Rights Reserved.