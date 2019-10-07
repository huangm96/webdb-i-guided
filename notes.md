# Notes

## Menu

- Introduction to RDBMS
- SQL
- Knex ++
- CRUD operations persisting data

R = Relational

DB = Database

M = Management

S = System

A Relation is similar to a spreadsheet, it has rows with columns.

Another name for a Relations is: **Table** .

The data on a Relational Database is stored in **Tables** . 

[Client] <HTTP (methods/endpoints/JSON data)> [API running on a Web server] <> [Database Management System]

Some polular DBMS
- Oracle
- MySQL
- PostgreSQL
- MS SQL Server
- SQLite3 (file-based RDBMS)
- MongoDB (No [Not Only] SQL database)

HTTP is a network protocol. A protocol is a set of rules for communication over the network

Each database vender can (and probably will) have it's own protocol.

SQL = Structured Query Language. SQL is a standard.

Each DBMS will implement part of the SQL standard and add extra features on top.

some SQL commands: https://www.w3schools.com/Sql/tryit.asp?filename=trysql_select_top

- SELECT * FROM Customers;
- SELECT customerName FROM Customers;
- SELECT customerName name, CustomerID as ID FROM Customers;
- select * from [Products]

```sql
select * from [Products] 
where price > 45
```

```sql
 select * from [Products] 
 where price >45 
 order by price desc
```

```sql
select * from [Customers] 
where country = 'Germany'
```

```sql
select country, city, * from [Customers] 
where country = 'Germany' 
order by country, city
```

```sql
select country, city, * from [Customers] 
where country = 'Germany' or country = 'Argentina' 
order by country, city
```

```sql
select country, city, * from [Customers] 
where country in( 'Germany' ,'Argentina') 
order by country, city
```

```sql
select country, city, * from [Customers] 
where country in( 'Germany' ,'Argentina') 
order by country, city 
limit 5
```

```sql
insert into Categories ('description', 'categoryName')
values ('swags','Lambda Swag')
```
```sql
update categories set description = 'Lambda School Swag', categoryName = 'The swag'
-- select * from categories
where categoryId = 9
```
```sql
delete from categories
--select * from categories
where categoryID = 8
```

## Connect to a DBMS from our API

[API] <= JS => [Knex] <- SQL -> [DB Driver] <= DBMS Protocol => [DBMS]

npm i knex sqlite3