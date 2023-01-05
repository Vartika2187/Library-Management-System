# Library-Management-System 📖
This is a Library Management System project which uses Java (GUI &amp; Backend) and MySQL (Database). 

### MYSQL has been used for database in this project. It contains 4 tables :-

Book : This table contains fields like ISBN, Title, Author, Quantity and Price.

Admin: This table contains fields like User_id and Password.

Student: This table contains fields like Student_ID, Name, Course, Branch and Year.

Record: This table contains fields like Return_Date, ISBN, Student_id and Issue_Date.

MYSQL setup :-

Create all the tables beforehand

<b>Creating Database</b>

CREATE DATABASE library_management_system;

USE library_management_system;

💎Create Book Table

<i>CREATE TABLE Book(ISBN int primary key, Title varchar(20) not null, Author varchar(20) not null, Price int default 0, Quantity int default 0,CHECK (Price>=0),CHECK (Quantity>=0));</i>

💎Create Student Table

<i>CREATE TABLE Student(SID int primary key, Name varchar(20) not null, Course varchar(20) not null, Branch varchar(20) not null, Email varchar(30) not null );</i>

💎Create Issue_Book Table

<i>CREATE TABLE Issue_Book (ISBN int, SID int,IssueDate date not null, foreign key Fk1(ISBN) references Book(ISBN),foreign key Fk2(SID) references Student(SID) );</i> 

💎Create Return_Book Table

<i>CREATE TABLE Return_Book (SID int,ISBN int, ReturnDate date not null, foreign key Fk1(SID) references Student(SID),foreign key Fk2(ISBN) references Book(ISBN) );</i>

💎Create Record Table

<i>CREATE TABLE Record (SID int, ISBN int, IssueDate date default null, ReturnDate date default null,foreign key Fk1(SID) references Student(SID), foreign key Fk2(ISBN) references Book(ISBN) ); </i>

Good to go!
