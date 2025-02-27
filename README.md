# ETL_pipeline

As an analytics engineer, my role is to automate processes to help provide faster access to a user-friendly product catalog for my data users.

Generally, analysts on the team have to manually retrieve and clean data every quarter to understand changes in sales and the capabilities of different energy types. This process typically takes days and is something most analysts dread. My job is to automate this process by building a data pipeline.

Below is my plan for writing a data pipeline that will pull data each month, enabling more rapid insights and freeing up time for my data consumers.

1. First, I defined an 'extract_tabular_data()' function to ingest tabular data.
- This function will take a single parameter, file_path. If file_path ends with .csv, use the pd.read_csv() function to extract the data.
- If file_path ends with .parquet, use the pd.read_parquet() function to extract the data.
- Otherwise, raise an exception and print the message: *"Warning: Invalid file extension. Please try with .csv or .parquet!".*

2. Next, I created another function with the name 'extract_json_data()', which takes a file_path. Use the json_normalize() function from the pandas library to flatten the nested JSON data, and return a pandas DataFrame.

3. After, I built a function to transform the electricity sales data. To do that, I created a function called 'transform_electricity_sales_data()' which takes a single parameter raw_data (should be of type pd.DataFrame.) The transform_electricity_sales_data() is used to fullfill needs and requirements collected from data users.

4. Lastly, to load a DataFrame to a file, I defined one more function called load(), which takes a DataFrame and a file_path.
- If the file_path ends with .csv, load the DataFrame to a CSV file.
- If instead the file_path ends with .parquet, load the DataFrame to a Parquet file.
- Otherwise, raise an exception that outputs a message in this format: *"Warning: {filepath} is not a valid file type. Please try again!_"*

**See complete code in "Building an ETL Pipeline" directory**
