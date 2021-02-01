# Banking-Management-System
Bank Management System with Python &amp; MySQL

This is one of the important project that almost all computer Science students should do. Bank Management Python MySQL System helps us to understand the different techniques of Database but also helps them to understand the business model and software that needs to follow. 

Database of Banking management System is maintained in MySQL tables: Customer and Transaction

A. Here is the Strcture of Customer Table as it follows:
Note: 
  1. account number(acno in Field column) is defined as a primary key as well as it will auto_increment.
  2. account number will also serve as foreign key in Transaction Table.
  
  mysql> desc customer;
  +-----------+--------------+------+-----+---------+----------------+
  | Field     | Type         | Null | Key | Default | Extra          |
  +-----------+--------------+------+-----+---------+----------------+
  | acno      | int(11)      | NO   | PRI | NULL    | auto_increment |
  | name      | char(30)     | YES  |     | NULL    |                |
  | address   | varchar(100) | YES  |     | NULL    |                |
  | phone     | varchar(15)  | YES  |     | NULL    |                |
  | email     | varchar(80)  | YES  |     | NULL    |                |
  | aadhar_no | varchar(20)  | YES  |     | NULL    |                |
  | acc_type  | varchar(20)  | YES  |     | NULL    |                |
  | status    | char(15)     | YES  |     | NULL    |                |
  | balance   | float(15,2)  | YES  |     | NULL    |                |
  +-----------+--------------+------+-----+---------+----------------+
  9 rows in set (0.03 sec)

B.Here is the strcure of second table which is Transaction Table:

  mysql> desc transaction;
  +--------+----------+------+-----+---------+----------------+
  | Field  | Type     | Null | Key | Default | Extra          |
  +--------+----------+------+-----+---------+----------------+
  | tid    | int(11)  | NO   | PRI | NULL    | auto_increment |
  | dot    | date     | YES  |     | NULL    |                |
  | amount | int(10)  | YES  |     | NULL    |                |
  | type   | char(20) | YES  |     | NULL    |                |
  | acno   | int(10)  | YES  |     | NULL    |                |
  +--------+----------+------+-----+---------+----------------+
  5 rows in set (0.02 sec)

C. Initial Data from Customer and Transaction Tables:
  
  mysql> select * from customer;
  +------+----------------+-------------------+-------------+------------------------+----------------+----------+--------+----------+
  | acno | name           | address           | phone       | email                  | aadhar_no      | acc_type | status | balance  |
  +------+----------------+-------------------+-------------+------------------------+----------------+----------+--------+----------+
  |    1 | rakesh kumar   | cf-4 surya nagar  | 987181818   | support@cbsetoday.com  | 1234-1243-4545 | saving   | active | 12200.00 |
  |    2 | raju vashistha | A-75-B Brij vihar | 96734344318 | raju@cbsetoday.com     | 4545-1243-4545 | current  | active | 10000.00 |
  |    3 | archana        | cf04              | 4545456     | archana@bianrynote.com | 1234-5656-4545 | saving   | active | 10000.00 |
  |    4 | ashutosh       | d-100 brij vihar  | 1122334455  | ashu@gmail.com         | 1124-5656-6576 | saving   | active | 56000.00 |
  |    5 | raman singh    | e-40 radha bihar  | 3344556677  | raman@yahoo.com        | 4455-5656-4545 | saving   | close  | 20000.00 |
  +------+----------------+-------------------+-------------+------------------------+----------------+----------+--------+----------+

  mysql> select * from transaction;
  +-----+------------+--------+----------+------+
  | tid | dot        | amount | type     | acno |
  +-----+------------+--------+----------+------+
  |   1 | 2020-10-16 |   2000 | deposit  |    1 |
  |   2 | 2020-10-15 |   2000 | deposit  |    2 |
  |   3 | 2020-10-18 |   1200 | withdraw |    1 |
  |   4 | NULL       |   2000 | deposit  |    1 |
  |   5 | 2020-11-30 |    200 | deposit  |    1 |
  |   6 | 2020-11-30 |   2000 | withdraw |    1 |
  |   7 | 2020-11-30 |    200 | withdraw |    1 |
  +-----+------------+--------+----------+------+
  
 Tips:
 MySQL.connector is used to make a secure connection between MySQL and Python. 
 
