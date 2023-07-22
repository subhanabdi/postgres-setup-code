# Start Postgres Here

## PGAdmin download link

https://www.pgadmin.org/download/

## Connection string

```
username:password@hostname:PORTNUMBER/Databasename
```

e.g.

```
postgres://default:Hb1rsM2CcqUi@ep-restless-hill-527417.us-east-1.postgres.vercel-storage.com:5432/verceldb
```

username: default
password: Hb1rsM2CcqUi
hostname: ep-restless-hill-527417.us-east-1.postgres.vercel-storage.com
Port: 5432
Maintenance Database: verceldb

## Navigate to tables in pgadmin

Databases->Verceldb->Schemas->public->Tables

## Database basic concepts - Good enough for hackathon projects

Select from table
create database, create table
insert into table (single row or multiple rows)
update row
delete row/rows from a table
drop table
primary , foreign key
JOINS ( inner join)
where (with and/or)

## Database intermediate/advanced concepts

JOIN (left join, right join, outer join)
order by asc/desc, limit
LIKE % operator
sub queries
cursors
stored procedures, triggers, function

## Select in postgres

```
select * from todo;
```

### select with limit 5

```
select * from todo limit 5
```

### select with order by and limit 5

```
select * from todo  order by id desc limit 5
```

### select with where clause

```
select * from todo where task='asdf' and id=4
```

## Insert into table

```
insert into todo2 (id,task) values
(1, 'task 1'),
(2, 'task 2')
```

### Tip/Common mistake

dont add comma at the end, when entering multiple values

```
insert into todo2 (id,task) values
(1, 'task 1'),
(2, 'task 2'),
```

## Update table

```
update todo2 SET task='updated task 1' where id =1
```

### Note that if no where clause is mentioned, it will update all rows of the table

```
update todo2 SET task='updated task 1'
```

## Delete from a table

<b>Step 1: First run select query to make sure everything is correct which is to be deleted</b>

```
select * from todo2 where id > 3
```

<b>Step 2: Covert `select *` to `delete`</b>

```
delete from todo2 where id > 3
```

## Drop table

```
drop table manager
```

## INNER JOIN

Create table employee

```
create table Employee(
emp_id int primary key,
emp_fname varchar not null,
emp_lname varchar not null,
location varchar(30) );
```

create table department

```
Create table department
(dept_id int primary key,
 emp_id int not null,
 dept_name varchar NOT NULL);
```

Join statement

```
SELECT first_name, last_name, dept_name
FROM Employee
INNER JOIN department
ON Employee.emp_id = department.emp_id;
```
