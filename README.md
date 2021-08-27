# PYTHON MySQL
Python can be used in database applications. 
One of the most popular database in MySQL

### MySQL Database
#### Prerequisites
Download and install MySQL on your computer.
[MySQL Website Link](https://www.mysql.com/downloads/ "MySQL site")

### Install MySQL Driver
Python needs a MySQL driver to access the MySQL database.
We will use the driver `MySQL Connector` from the PIP Python environment to install it
* Download and install "MySQL Connector":
  ##### `python -m pip install mysql-connector-python`

#### Test MySQL Connector
To test if the installation was successful, or if you already have "MySQL Connector" installed, create python page with the following content:
Example:- `demo_mysql_text.py`

If the above code was executed with no errors, "MySQL Connector" is installed and ready to be used.

#### Create Connection
- Start by creating a connection to the database.
Use the username and password from our MySQL database:
Example:- `demo_mysql_connection.py`


# PYTHON MySQL Create Database (Folder)
### Creating a Database
- To create a data bse in MySQL, use the `CREATE DATABASE` statement:
Example:- `mysqlcreate_database.py` *Create a database named `mydatabase`*
If the above code is executed without no errors, you have successfully created a database.

### Check if Database Exists
- You can check if a database exist by listing all databases in your system by using the `SHOW DATABASES` statement:
Example:- `check_database_show.py` 
- Or You can try to access the database when making the connection:
Example:- `check_database_access_connection.py`
* If database doesn't exist you'll get an error*


# PYTHON MySQL Create Table (Folder)
#### Creating a Table
- To create a table in MySQL, use the `CREATE TABLE` statement.
- Make sure you define the name of the database when you create the connection
Example:- `create_table.py`

#### Check If Table Exists
- You can check if a table exists by listing all tables in your database with the "SHOW TABLES" statement:
Example:- `check_table_exists.py` *Return a list of your system's database*

#### Primary Key
- When creating a table, you should also create a column with a unique key for each record. This can be done by defining a `PRIMARY KEY`
- The statement `INT AUTO_INCREMENT PRIMARY KEY` which will insert a unique number for each record. Starting at 1, and increased by one for each record.
Example:- `create_primary_key.py`
*If table already exists, use the ALTER TABLE keyword:*
Example:- `create_primary_key_existing_table.py`


# PYTHON MySQL Insert Into Table (Folder)["./"]
#### Insert Into Table
To fill a table in MySQL, use the "INSERT INTO" statement.
Example:- `insert_into.py` *Insert a record in the "customers" table:* 

- * Important: Notice the statement: `mydb.commit()`. It's required to make the changes, otherwise no changes are made to the table.

### Insert Multiple Rows
- To insert multiple rows into a table, use the `executemany()` method.
The second parameter of the `executemany()` method is a list of tuples, containing the data you want to insert:
Example:- `insert_multiple_rows.py`

### Get Inserted ID
You can get the id of the row you just inserted by asking the cursor object.
*  NOTE: If you insert more than one row, the id of the last inserted row is returned.
Example:- `insert_onerow_return_id.py`