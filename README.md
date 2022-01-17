>***Relational schemas*** 
* depict how a database is organized
* like a *blueprint*, or a plan for a database
* heps a lot while writing your queries

> ***Primary key* - unique identifier**  - a column(or a set of columns) whose value exists and is unique for every record in a table.
 * Each table can have only one primary key
 * Not all the tables have a primary key
 * Cannot contain null values

> ***Foreign key*** 
 * a field (or fields) in one table that refers to the PRIMARY KEY in another table
 * they show us where the relations are between tables

 > ***Unique key*** - used whenever you would like to specify that you don't want to see duplicate data in a given field
 * Can contain null values
 * Can have multiple unique keys in a table

 > ***Relationships*** - tell you how much of the data from a foreign key field can be seen in the primary key column of the tablethe data is related to and vice versa:
* *one-to-many (many-to-one)* type of relationship:  **one** value from a primary key from x table can be found **many** times in the foreign key in y table
* *one-to-one*
* *many-to-many*

---

## *SQL* is a declarative programing language to create and manipulate relational databases

Components of SQL syntax:

* **DDL - Data Definition Language** (*Creation of data*)- a set of statements that allow the user to define or modify data structures and objects(ex: tables)
    * *The **CREATE** statement* - used for creating entiredatabases and database objects as tables

    #### General Syntax:

    `CREATE object_type object_name;`
    
    #### Create Table Syntax:

    `CREATE TABLE object_name (column_name data_type);`

    * *The **ALTER** statement* - used when altering existing objects
     * **ADD** : 
      `ALTER TABLE table_name ADD COLUMN column_name data_type;`
    * *The **DROP** statement* - used to delete objects:

        `DROP object_type object_name;`

    * To delete only the content of the table and continue to use the table as a object in the database use *the **TRUNCATE** statement* :

        `TRUNCATE object-type object_name;`
    * *The **RENAME** statement* - used to rename the object :

        `RENAME object_type object_name TO new_object_name;`

---

* **DML - Data Manipulation Language** (*Manipulation of Data*) - a set od statements that allow us to manipulate the data in the tables of a database:
    * *The **SELECT** statement* - used to retrieve data from database objects(ex: tables)

        `SELECT column_name FROM table_name;`
    * *The **INSERT** statement* - used to insert data into tables:

        `INSERT INTO table_name (column_names) VALUES (coresponding_values);`
    * *The **UPDATE** statement* - allows you to renew existing data of your tables:
        `UPDATE table_name SET column_name=new_value WHERE condition;`
    * *The **DELETE** statement* - allows us todelete only specified record:
        `DELETE FROM table_name WHERE condition;` 
---

* **DCL - Data Control Language** (*Assignment and removal of permissions to use this data*)- allows us to manage the rights users have in a database:
    * *The **GRANT** statement* - gives (or grants) certain permissions to users (complet or partial)

        `GRANT type_of_permition ON database_name.table_name TO 'username'@'localhost';`
    * *The **REVOKE** statement* - revokes permissions and privileges of database users:
        `REVOKE type_of_permition ON database_name.table_name TO 'username'@'localhost';`

---

* **TCL - Transaction Control Language**(*Saving and restoring changes to a database*)
    * *The **COMMIT** statement* :
     * related to *INSERT*, *DELETE*, *UPDATE*
     * will save changes you've made
     * will let other users to have access to the modified version of the database
     * changes cannot be undone

    * *The **ROLLBACK** clause* :
     * allows you to take a step back to the last non-committed state
     * the last change(s) made will not count
