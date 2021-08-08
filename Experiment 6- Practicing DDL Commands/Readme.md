### AIM: Practicing DDL Commands.

#### Data Definition Language:

The data definition language is used to create an object, alter the structure of an object and also drop 
already created object. The Data Definition Languages used for table definition can be classified into 
following:

- Create table command
- Alter table command
- Truncate table command
- Drop table command

#### Creating of Tables on ROAD WAY TRAVELS:

Table is a primary object of database, used to store data in form of rows and columns. It is created 
using following command:

```` 
Create Table <table_name> (column1 datatype (size), column2 datatype (size), ・_, column (n) 
datatype (size));
```
Where, table_name is a name of the table and coulumn1, column2 _ column n is a name of the column 
available in table_name table. R Each column is separated by comma. Pointes to be remember while 
creating a table. Table Name must be start with an alphabet. Table name and column name should be 
of maximum 30 characters long. Column name should not be repeated in same table.

Reserve words of Oracle cannot be used as a table and column name.

Two different tables should not have the same name.

Underscores, numerals and letters are allowed but not blank space or single quotes.

#### Example:

```
SQL> create table Bus (Bus_No varchar (5), source varchar (20), destination varchar (20), 
CouchType varchar2 (10), fair number);
```
Table Created.

Above definition will create simple table. Still there are more additional option related with create 
table for the object-relation feature we will discuss it afterwards.

### Desc command:

Describe command is external command of Oracle. The describe command is used to view the 
structure of a table as follows.

```
Desc <table name>
```
```
SQL> desc bus;
```
Name Null? Type
----------------------------------------- -------- ----------------------------

BUS_NO NOT NULL INTEGER2 (5)
SOURCE VARCHAR2 (20)
DESTINATION VARCHAR2 (20)
CouchType VARCHAR2 (10)
FAIR NUMBER

### Reservation Table:
```
SQL> create table Reservation (PNR_NO Numeric (9), No_of_seats Number (8), Address varchar 
(50), Contact_No Numeric (9), Status char (3));
```
Table created.
```
SQL> desc Reservation
```
Name Null? Type
----------------------------------------- -------- ----------------------------
PNR_NO NUMBER (9)
NO_OF_SEATS NUMBER (8)
ADDRESS VARCHAR2 (50)
CONTACT_NO NUMBER (9)
STATUS CHAR (3)

### Cancellation Table:
```
SQL> create table Cancellation (PNR_NO Numeric (9), No_of_seats Number (8), Address 
varchar (50), Contact_No Numeric (9), Status char (3));
```
Table created.
```
SQL> desc Cancellation
```
Name Null? Type
----------------------------------------- -------- ----------------------------
PNR_NO NUMBER (9)
NO_OF_SEATS NUMBER (8)
ADDRESS VARCHAR2 (50)
CONTACT_NO NUMBER (9)
STATUS CHAR (3)

### Ticket Table:
```
SQL> create table Ticket(Ticket_No Numeric(9) primary key, age number(4), sex char(4) Not 
null, source varchar(2), destination varchar(20), dep_time varchar(4));
```
Table created.
```
SQL> desc Ticket
```
Name Null? Type
----------------------------------------- -------- ----------------------------
TICKET_NO NOT NULL NUMBER (9)
AGE NUMBER (4)
SEX NOT NULL CHAR (4)
SOURCE VARCHAR2 (2)
DESTINATION VARCHAR2 (20)
DEP_TIME VARCHAR2 (4)

#### Alteration of Table:

Once Simple Table is created, if there is a need to change the structure of a table at that time alter
command is used. It is used when a user want to add a new column or change the width of data type or 
data type itself or to add or drop integrity constraints or column. 

I.e. table can be altered in one of three ways: by adding column, by changing column definition or by
dropping column.

#### Addition of Column(s)
Addition of column in table is done using:

```
Alter table <table_name> add (column1 datatype, column2 datatype ・_);
```
Add option is used with alter table_ when you want to add a new column in existing table. If you 
want to Add more than one column then just write column name, data type and size in brackets. As 
usual Comma sign separates each column. For Example, suppose you want to add column comm in 
emp_master, then you have to perform the following command.

```
SQL> ALTER TABLE Passenger ADD FOREIGN KEY (PNR_NO) REFERENCES Reservation 
(PNR_NO);
```
Table altered.

```
SQL> ALTER TABLE Cancellation ADD FOREIGN KEY (PNR_NO) REFERENCES 
Reservation (PNR_NO);
```
Table altered.
```
SQL> alter table Ticket modify tiketnonumber (10);
```
Table altered.

#### Deletion of Column:

Till Oracle8 it is not possible to remove columns from a table but in Oracle8i, drop option is used 
with Alter table_ when you want to drop any existing column.

```
Alter table <table_name> drop column <column name>;
```
Using above command you cannot drop more than one column at a time.
For Example, suppose you want to delete just before created column comm from the emp_master, then 
you have to apply following command.

```
SQL>Alter Table Emp_master drop column comm;
```
Table altered.

Dropping column is more complicated than adding or modifying a column, because of the additional 
work that Oracle has to do. Just removing the column from the list of columns in the table actually 
recovers the space that was actually taken up by the column values that is more complex, and 
potentially very time- consuming for the database. For this reason, you can drop a 
Column using unused clause. 

Column can be immediately remove column by drop clause, the action may impact on performance or 
one make marked column as unused using unused clause, there will be no impact on performance. 
When unused caluse is used the column can actually be dropped at a later time when the database is 
less heavily used. One can marked column as a unused using:

```
Alter table <table_name> set unused column <column name>;
```

For Example:

```
SQL>Alter Table Emp_master set unused column comm.;
```
Table altered.

Making a column as Unused_ does not release the spcace previously used by the Column, until you 
drop the unused columns. It can be possible using:
```
Alter table <table_name> drop unused columns;
```
Once you have marked column as unused_ you cannot access that column
You can drop multiple columns at a time using single command as per follows
```
Alter table <table_name> drop (Column1, Column2,_);
```
The multiple columns name must be enclosed in parentheses.

### Modification in Column:

Modify option is used with Alter table_ when you want to modify any existing column. If you want to
modify data type or size of more than one column then just write column name, data type and size in
brackets and each column is separated by comma sign as per follows:

```
Alter table <table name> modify (column1 datatype, ・_);
```
For Example, if you want to change size of salary column of emp_master the following command is
performed.
```
SQL> Alter table emp_master modify salary number (9, 2);
```
Table altered.

It will change size of salary column from 7 to (9, 2).
When you want to decrease the size of column, table must be empty. If table has any rows then it will 
not allow decrement in the column width.

### Truncate Table:
If there is no further use of records stored in a table and the structure is required then only data can be 
deleted using truncate command. Truncate command will delete all the records permanently of 
specified table as follows.

```
Truncate table <table name> [Reuse Storage];
```

Example:

Following command will delete all the records permanently from the table.

```
SQL>Truncate Table Emp_master;
```
Or

```
Truncate Table Emp_master Reuse Storage;
```
Table truncated.
