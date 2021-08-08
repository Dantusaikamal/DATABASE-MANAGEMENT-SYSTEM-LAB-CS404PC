## AIM: Practicing DML commands.

### Data Manipulation Command:

Data Manipulation commands are most widely used SQL commands and they are

- Insert
- Update
- Delete
- Select

#### a) Insert command:

After creation of table, it is necessary it should have data in it. The insert command is used to add data 
in form of one or more rows to a table as per follows:
Insert into <table name> values (a list of data values);
 In a list of data values you have to specify values for each and every column in the same order as 
they are defined. A value of each column is separated by comma in the list.

The value of char, nchar, and varchar2, nvarchar2, raw, long and date data types are enclosed in single 
quotes.

Using insert command one can insert values in specific columns as follows:
Insert into <table name> (column list) values (a list of data);

Here number of column and a list of data should be same and list of data should be in order to column 
list.

```
SQL> insert into emp_master (empno, ename, salary) values (1122, ‘Smith’, 8000);
```
1 row created.

Above command insert one row but values are inserted in only three columns. Remaining four 
columns have null values. If you have defined not null constraint in any of remaining columns it wants 
allow you to insert data in a table.

#### Adding values in a table using Variable method:

Till now we have seen static method to insert data. One can add data in a table using variable method 
with & (ampersand) sign. It will prompt user to enter data of mention field. Generally It is used to add 
more than one row in a table without typing whole command repetitively using / sign.
```
SQL> insert into Passenger values (&PNR_NO,&TICKET_NO, '&Name', &Age, '&Sex', 
'&PPNO');
```

Enter value for pnr_no: 1
Enter value for ticket_no: 1
Enter value for name: SACHIN
Enter value for age: 12
Enter value for sex: m
Enter value for ppno: sd1234

Old one: 
```
insert into Passenger values (&PNR_NO, &TICKET_NO, '&Name', &Age, '&Sex', 
'&PPNO')
```
New one: 
```
insert into Passenger values (1, 1,'SACHIN', 12,'m','sd1234')
```
1 row created.

```
SQL> /

Enter value for pnr_no: 2
Enter value for ticket_no: 2
Enter value for name: rahul
Enter value for age: 34
Enter value for sex: m
Enter value for ppno: sd3456

Old 1: 
```
insert into Passenger values (&PNR_NO, &TICKET_NO, '&Name', &Age, '&Sex', 
'&PPNO')
```
New 1: 
```
insert into Passenger values (2, 2,'rahul', 34,'m','sd3456')
```
1 row created.

SQL> /
Enter value for pnr_no: 3
Enter value for ticket_no: 3
Enter value for name: swetha
Enter value for age: 24
Enter value for sex: f
Enter value for ppno: sdqw34

old 1: 
```
insert into Passenger values(&PNR_NO,&TICKET_NO, '&Name', &Age, '&Sex', '&PPNO')
```

new 1: 
```
insert into Passenger values(3,3,'swetha',24,'f','sdqw34')
```
1 row created.

SQL> /
Enter value for pnr_no: 4
Enter value for ticket_no: 4
Enter value for name: ravi
Enter value for age: 56
Enter value for sex: m
Enter value for ppno: sdqazx

old 1: 
```
insert into Passenger values(&PNR_NO,&TICKET_NO, '&Name', &Age, '&Sex', 
'&PPNO')
```
new 1: 
```
insert into Passenger values(4,4,'ravi',56,'m','sdqazx')
```
1 row created.

SQL> /
Enter value for pnr_no: 4
Enter value for ticket_no: 5
Enter value for name: asif
Enter value for age: 33
Enter value for sex: m
Enter value for ppno: iuyhjk

old 1: 
``insert into Passenger values(&PNR_NO,&TICKET_NO, '&Name', &Age, '&Sex', 
'&PPNO')
```
new 1: 
```insert into Passenger values(4,5,'asif',33,'m','iuyhjk')
```
```insert into Passenger values(4,5,'asif',33,'m','iuyhjk')```
*
ERROR at line 1: ORA-00001: unique constraint (SYSTEM.SYS_C004023) violated
```
SQL> insert into Bus values('&Bus_No','&source','&destination');
```
Enter value for bus_no: 1
Enter value for source: hyd
Enter value for destination: ban

old 1: 
``` insert into Bus values('&Bus_No','&source','&destination')
new 1: 
``` insert into Bus values('1','hyd','ban')
1 row created.

SQL> /
Enter value for bus_no: 2
Enter value for source: hyd
Enter value for destination: chn

``` old 1: insert into Bus values('&Bus_No','&source','&destination')
``` new 1: insert into Bus values('2','hyd','chn')

1 row created.

SQL> /
Enter value for bus_no: 4
Enter value for source: hyd
Enter value for destination: mum

``` old 1: insert into Bus values('&Bus_No','&source','&destination')
``` new 1: insert into Bus values('4','hyd','mum')
1 row created.

SQL> /
Enter value for bus_no: 5
Enter value for source: hyd
Enter value for destination: kol

``` old 1: insert into Bus values('&Bus_No','&source','&destination')
``` new 1: insert into Bus values('5','hyd','kol')
1 row created.
SQL> /
Enter value for bus_no: 5
Enter value for source: sec
Enter value for destination: ban
``` old 1: insert into Bus values('&Bus_No','&source','&destination')
``` new 1: insert into Bus values('5','sec','ban')
insert into Bus values('5','sec','ban')
*
ERROR at line 1:
ORA-00001: unique constraint (SYSTEM.SYS_C004025) violated

``` SQL> insert into Reservation values(&PNR_NO, &No_of_seats, '&Address', &Contact_No , 
'&Status');
Enter value for pnr_no: 1
Enter value for no_of_seats: 2
Enter value for address: masabtank
Enter value for contact_no: 9009897812
Enter value for status: s


EMPNO ENAME JOB HIREDATE SALAR DEPTNO COMM
1122 Allen Manager 1-JAN-00 10000 10 1000
1122 Smith 1-JAN-00 8000
1123 King Clerk 30-JUN-00 3400 20 300
1124 Martin Manager 30-AUG-00 7000 20 1000
1125 Tanmay 16-SEP-00 10

5 rows selected.

```
SQL> select empno, ename,salary from emp_master;
```
This query will give information from only three columns.

EMPNO ENAME SALARY
1122 Allen 10000
1122 Smith 8000
1123 King 3400
1124 Martin 7000
5 rows selected.

```
SQL> select * from Passenger;
```
PNR_NO TICKET_NO NAME AGE SEX PPNO
---------- ---------- -------------------- ---------- ---------- ---------------
 1 1 SACHIN 12 m sd1234
 2 2 rahul 34 m sd3456
 3 3 swetha 24 f sdqw34
 4 4 ravi 56 m sdqazx

#### Select Command:
Previously we have seen simple use of select statement to retrieve the data from the table. Now we 
have look further use of Select statement.

#### Distinct Clause

To prevent the selection of distinct rows, we can include distinct clause with select command.The 
following command will exclude duplicate empno.

```
SQL> select distinct deptno from emp_master;
```
DEPTNO
10
20
2 rows selected.


#### UPDATE Table:

```
SQL> update Passenger set age='43' where PNR_NO='2';
```
1 row updated.

```
SQL> select * from Passenger;
```
PNR_NO TICKET_NO NAME AGE SEX PPNO
---------- ---------- -------------------- ---------- ---------- ---------------
 1 1 SACHIN 12 m sd1234
 2 2 rahul 43 m sd3456
 3 3 swetha 24 f sdqw34
 4 4 ravi 56 m sdqazx

#### DELETE:
```
SQL> delete from Passenger where PNR_NO='4';
```
1 row deleted.

```
SQL> select * from Passenger;
```
PNR_NO TICKET_NO NAME AGE SEX PPNO
---------- - --------- -------------------- ---------- ---------- ---------------
 1 1 SACHIN 12 m sd1234
 2 2 rahul 43 m sd3456
 3 3 swetha 24 f sdqw34

#### DROP Table:
```
SQL> drop table Cancellation;
```
Table dropped.
