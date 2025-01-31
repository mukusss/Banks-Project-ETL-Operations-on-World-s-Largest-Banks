
# Banks Project: ETL Operations on World's Largest Banks

This is coursera IBM Data Engineering Certification (Python Project for Data Engineering) project.

This project demonstrates an end-to-end ETL (Extract, Transform, Load) process to acquire, process, and store information on the world's largest banks by market capitalization. The project utilizes web scraping, data transformation, and database operations to automate reporting for financial data.


## Project Overview
**The project automates the following tasks:**

- Extracting data from a Wikipedia page.

- Transforming the data by converting market capitalization to different currencies (GBP, EUR, INR).

- Storing the processed data in both CSV and SQLite database formats.

- Running queries on the database table to generate insights.
## Key Features
- **Web Scraping:** Uses BeautifulSoup to extract tabular data from the web.

- **Data Transformation:** Converts market capitalization from USD to other currencies using provided exchange rates.

- **Data Storage:** Saves the transformed data in a CSV file and an SQLite database table.

- **SQL Queries:** Executes queries on the database table to extract insights.

- **Logging:** Logs the progress of each step to a code_log.txt file.
## Prerequisites
- Python 3.10 or later.

**Required Python libraries:**

- beautifulsoup4, pandas, numpy ,sqlite3 (part of Python's standard library)


## Project Files
- **banks_project.py:** Main Python script containing the ETL code.

- **exchange_rate.csv:** File containing exchange rate information.

- **Largest_banks_data.csv:** Output file containing transformed data in CSV format.

- **Banks.db:** SQLite database containing the processed data.

- **code_log.txt:** Log file recording the progress of each task.
## Execution Instructions
1. Ensure all prerequisite libraries are installed and exchange_rate.csv is downloaded in the same directory as the script.

2. Save the Python script (banks_project.py) in the same directory.

3. Run the script from the terminal or command prompt:

**python banks_project.py**

4. After execution:

- Check **Largest_banks_data.csv** for the processed data in CSV format.

- Open **Banks.db** using an SQLite viewer to inspect the database table.

- Review **code_log.txt** for progress logs.
## Script Workflow
1. Extract:
- Scrapes data from the Wikipedia page under the heading "By market capitalization".
- Converts data into a Pandas DataFrame.

2. Transform:
- Reads **exchange_rate.csv** to get currency conversion rates
- Adds new columns for market capitalization in **GBP**, **EUR**, and **INR**.

3. Load:

- Saves the transformed data to **Largest_banks_data.csv**.
- Loads the data into the SQLite database **(Banks.db)** under the table Largest_banks.

4. Query:

- Executes SQL queries to:

    -    Retrieve the entire table.

    - Calculate the average market capitalization in GBP.

    - Retrieve the top 5 banks by name.


## SQL Queries Used
1. Retrieve the entire table:
-           SELECT * FROM Largest_banks;

2. Calculate average market capitalization in GBP:
-       SELECT AVG(MC_GBP_Billion) FROM Largest_banks;

3. Retrieve names of the top 5 banks:
-       SELECT Name FROM Largest_banks LIMIT 5;

## Conclusion
This project provides hands-on experience with Python-based ETL pipelines, showcasing the integration of web scraping, data transformation, and database operations. It is designed for repetitive execution, making it suitable for quarterly financial reporting tasks.