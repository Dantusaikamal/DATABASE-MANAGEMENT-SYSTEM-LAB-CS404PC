## AIM: Normalization.

Until now we have created table without using any constraint, Hence the tables have not been given 
any instructions to filter what is being stored in the table.

The following are the types of integrity constraints 
1. Domain Integrity constraints
2. Entity Integrity constraints
3. Referential Integrity constraint
4. Oracle allows programmers to define constraints
5. Column Level
6. Table Level

### Column Level constraints:
 
 If data constraints are defined along with the column definition when creating or altering a table 
structure, they are column level constraints. Column level constraints are applied to the current 
column. The current column is the column that immediately precedes the constraints i.e. they are local 
to a specific column. Column level constraints cannot be applied if the data constraints span across the 
multiple columns in a table.
Table Level Constraint:
 
 If the data constraints are defined after defining all the table columns when creating or altering a 
table structure, it is a table level constraint. Table Level constraints mostly used when data constraints 
spans across multiple columns in a table.

### Domain Integrity Constraints:

These constraints set a range and any violations that take place will prevent the user from performing 
the manipulations that caused the breached.

### Entity Integrity Constraints:
T
his type of constraints are further classified into
1. Unique Constraint
2. Primary Key Constraint

### Unique Constraint:

The purpose of unique key is to ensure that information in the column(s) is unique i.e. the value 
entered in column(s) defined in the unique constraint must not be repeated across the column. A table 
may have many unique keys. If unique constraint is defined in more than one column (combination of 
columns), it is said to be composite unique key. Maximum combination of columns that a composite 
unique key can contain is 16.

### Primary Key Constraint:
 
 A primary key is one or on more columns(s) in a table to uniquely identify each row in the table. A 
primary key column in a table has a special attribute. It defines the column, as a mandatory column i.e. 
the column cannot be left blank and should have a unique value. Here by default not null constraint is 
attached with the column. A multicolumn primary key is called a Composite primary key. The only 
function of a primary key in a table is to uniquely identify a row. A table can have only one primary 
key.

### Referential Integrity Constraint:
 
 In this category there is only one constraint and it is Foreign Key & References to establish a Parentchild_ or a Master-detail_ relationship between two tables having a common column, we make use of 
referential integrity constraint. Foreign key represent relationships between tables. A foreign key is a 
column whose values are derived from the primary key or unique key. The table in which the foreign 
key is defined is called a foreign table or Detail table. The table that defines the primary or unique keys 
and is referenced by the foreign key is called the Primary table or Master table. The master table can be 
referenced in the foreign key definition by using references keyword. If the column name is not 
specified, by default, Oracle references the primary key in the master table.

The existence of a foreign key implies that the table with the foreign key is related to the master table
from which the foreign key is derived. A foreign key must have a corresponding primary key or a 
unique key value in a master table.

### Principles of Foreign Key Constraint:

Rejects an insert or update of a value in a particular column, if a corresponding value does not exist in
the master table.

Deletion of rows from the Master table is not possible if detail table having corresponding values.
Primary key or unique key must in Master table.
Requires that the foreign key column(s) and reference column(s) have same data type
References constraint defined at column level

### Example:

```
SQL> create table Passenger(PNR_NO Numeric(9) references reservation , Ticket NO 
Numeric(9) references ticket, Name varchar(20), Age Number(4), Sex char(10), PPNO 
varchar(15));
``` 
Table created.

### Foreign Key Constraint with alter command:

``` 
SQL> alter table reservation add constraint fk_icode foreign key (busno) references bus 
(bus_no);
```
Table altered.
