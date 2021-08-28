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


# PYTHON MySQL Create Database (Folder)["./MySQL Create Database/"]
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


# PYTHON MySQL Create Table (Folder)["./MySQL Create Table/"]
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


# PYTHON MySQL Insert Into Table (Folder)["./MySQL Insert/"]
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


# PYTHON MySQL Select From (Folder)["./MySQL Select/"]
### Select From a Table
- To select from a table in MySQL, use the "SELECT" statement:
Example:- `select_all_records.py` *Select all records and display the result*

* Note: We use the `fetchall()` method, which fetches all rows from the last executed statement.

### Selecting Columns
- To Select only some of the columns in a tables, use the "SELECT" statement followed by the column name(s):
Example:- `select_columns.py` *Select only the name and address columns*

### Using the fetchone() Method
* If you are interested in one row, you can use the `fetchone()` method.
- `fetchone()` will return the first row of the result:
Example:- `fetchone()_row.py` *Fetch one row only*


# PYTHON MySQL Where (Folder)["./MySQL Where/"]
### Select With a Filter
- When selecting records from a table, you can filter the selection by using the "WHERE" statement:
Example:- `select_where_filter.py` *Select record(s) where the address is "Park Lane 38": result*

### Wildcard Characters
- You can also select the records that starts, includes, or ends with a given letter or phrase.
- Use the `%` to represent wildcard characters:
Example:- `select_where_wildcards.py` *Select records where the address contains the word "way"* 

### Prevent SQL Injection
- When query values are provided by the user, you should escape the values. This is to prevent SQL injections, which is a common web hacking technique to destroy or misuse your database.
- The `mysql.connect` module has methods to escape query values:
Example:- `prevent_sql_injection.py` *Escape query values by using the placeholder `%s` method*


# PYTHON MySQL Order By (Folder)["./MySQL Order By/"]
### Sort the Result
- Use the `ORDER BY` statement to sort the result in ascending or descending order.
- The `ORDER BY` keyword sort the result the ascending by default. To sort the result in descending order, use the `DESC` keyword.
Example:- `sort_alphabetically.py` *Sort the result alphabetically by name: result:*

### Order By `DESC`
- Use the `DESC` keyword to sort the result in a descending order.
Example:- `sort_alphabet_descending.py` *Sort the result reverse alphabetically by name*


# PYTHON MySQL DElete From By (Folder)["./MySQL Delete/"]
### Delete Record
- Using the keyword `DELETE FROM` statement can delete records from an existing table.
Example:- `delete_from.py` *Delete any record where the address is "Mountain 21"*

* Important!: Notice the statement" `mydb.commit()`. It's required to make changes, otherwise no changes are made to the table.*
* Notice the WHERE clause in the DELETE syntax: The Where clause specifies which record(s) that should be deleted. If you omit the WHERE clause, all records will be deleted!

### Prevent SQL Injection
- It's considered a good practice to escape the values of any query, also in delete statements.
- This is to prevent SQL injections, which is a common web hacking technique to destroy or misuse your database.
- The `mysql.connector` module uses the placeholder `%s` to escape values in the delete statement:
Example:- `delete_prevent_sql_injection.py` *Escape values by using the placeholder `%s` method*


# Python MySQL Drop Table (Folder)["./MySQL Drop Table/"]
### Delete A Table
- You can delete an existing table by using the "DROP TABLE" statement:
Example: `delete_table.py` *Delete the table "customers"*

### Drop Only if Exist
- If the table you want to delete is already deleted, or for any other reason does not exists, you can use the `IF EXISTS` keyword to avoid getting an error.
Example:- `delete_table_if_exists.py`


# PYTHON MySQL Update Table (Folder)["./MySQL Update/"]
### Update Table
- You can update existing records in a table by using the "UPDATE" statement:
Example:- `update_table_address.py` *Overwrite the address column from "Valley 345" to "Canyoun 123"*

* Important!: Notice the statement" `mydb.commit()`. It's required to make changes, otherwise no changes are made to the table.*
* Notice the `WHERE` clause in the `DELETE` syntax: The Where clause specifies which record(s) that should be updated. If you omit the WHERE clause, all records will be updated!

### Prevent SQL Injection
- The `mysql.connector` module uses the placeholder `%s` to escape values in the delete statement:
Example:- `update_prevent_sql_injection.py` *Escape values by using the placeholder `%s` method* 


# PYTHON MySQL Limit
### Limit the result
- You can limit the number of records returned from the query, using the "LIMIT" statement:
Example:- `limit_records_count.py` *Select the 5 first records in the "customers" table* 

### Start From Another Position
- If you want to return five records, starting from the third record, the `OFFSET` keyword is used:
Example:- `limit_records_another_position.py` *Start from position 3, and return 5 records:*


# PYTHON MySQL Join (Folder)["./MySQL Join/"]
### Join Two or More Tables
- You can combine rows from two or more tables, based on a related column between them, by using a JOIN statement.
- Consider you have a "users" table and a "products" table:
#### Users
  { id: 1, name: 'John', fav: 154},
  { id: 2, name: 'Peter', fav: 154},
  { id: 3, name: 'Amy', fav: 155},
  { id: 4, name: 'Hannah', fav:},
  { id: 5, name: 'Michael', fav:}

#### Products
  { id: 154, name: 'Chocolate Heaven' },
  { id: 155, name: 'Tasty Lemons' },
  { id: 156, name: 'Vanilla Dreams' }

- These two tables can be combined by using users' `fav` field and products' `id` field.
Example:- `joining_tables.py`