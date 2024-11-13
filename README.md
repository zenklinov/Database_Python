# Python to PostgreSQL Connection Guide

This repository provides a Jupyter notebook that demonstrates how to connect Python to a PostgreSQL database. Using the `psycopg2` library, the notebook guides users through the essential steps of setting up, connecting, querying, and managing data in PostgreSQL directly from Python.

## Features

- Establish a connection between Python and PostgreSQL.
- Perform CRUD (Create, Read, Update, Delete) operations on a PostgreSQL database.
- Execute SQL queries from Python.
- Fetch and display query results.
- **Language is Indonesian**

## Requirements

To run this notebook, you need to have:

- Python installed
- PostgreSQL installed and configured
- Required Python libraries installed (`psycopg2` and optionally `pandas` for data handling)

### Installation

1. **Clone the repository**:
```bash
git clone https://github.com/zenklinov/Database_Python.git
cd Database_Python
```

2. **Install required libraries**: Install psycopg2 for PostgreSQL connection. Use the following command:
```bash
pip install psycopg2-binary
```
If you intend to manipulate data using pandas, install it with:
```bash
pip install pandas
```

## Notebook Overview
1. **Database Connection**:
- Set up connection parameters including host, database name, user, and password.
- Connect to PostgreSQL using ```psycopg2```.

2. Database Operations:
- **Creating tables**: Define and create tables within the PostgreSQL database.
- **Inserting data**: Insert sample data into tables.
- **Querying data**: Execute SELECT queries to retrieve data.
- **Updating and Deleting data**: Modify or delete records as needed.

3. **Handling Query Results**:
- Fetch and display query results in the notebook.
- Optional use of ```pandas``` to load data into DataFrames for easier manipulation and visualization.

## Usage
To use this notebook:
1. Open the ```Python_to_PostgreSQL```.ipynb file in Jupyter Notebook or JupyterLab.
2. Configure your database connection settings in the notebook, replacing placeholders with your PostgreSQL details.
3. Run each cell sequentially to establish a connection, create tables, insert data, and execute queries.

### Example
Below is an example of a simple query execution in the notebook:
```python
import psycopg2

# Connect to PostgreSQL
conn = psycopg2.connect(
    host="your_host",
    database="your_database",
    user="your_user",
    password="your_password"
)

# Create a cursor
cur = conn.cursor()

# Execute a query
cur.execute("SELECT * FROM your_table")

# Fetch results
rows = cur.fetchall()
for row in rows:
    print(row)

# Close the cursor and connection
cur.close()
conn.close()
```

Replace ```your_host```, ```your_database```, ```your_user```, ```your_password```, and ```your_table``` with your actual PostgreSQL credentials and table name.

## Troubleshooting
- **Connection errors**: Ensure PostgreSQL is running and your connection parameters are correct.
- **Permission errors**: Check user permissions for accessing the database.
- **Library errors**: Make sure ```psycopg2``` is installed properly. If using ```pandas```, confirm it is installed as well.
