-- Active: 1721212360747@@127.0.0.1@3306
CREATE DATABASE test;
use test;

CREATE TABLE orders_data
(
    cust_id int,
    order_id int,
    country VARCHAR(50),
    state VARCHAR(50)
);

INSERT INTO orders_data values(1,100,'USA','SEATTLE')
INSERT INTO orders_data values(2,101,'INDIA','UP');
INSERT INTO orders_data values(3,103,'INDIA','BIHAR');
INSERT INTO orders_data values(4,108,'USA','WDC');
INSERT INTO orders_data values(5,109,'UK','LONDON');
INSERT INTO orders_data values(6,110,'USA','WDC');
INSERT INTO orders_data values(7,120,'INDIA','AP');
INSERT INTO orders_data values(8,121,'INDIA','GOA');
INSERT INTO orders_data values(9,131,'USA','SEATTLE');
INSERT INTO orders_data values(10,142,'USA','SEATTLE');
INSERT INTO orders_data values(11,158,'USA','SEATTLE');
SELECT * FROM ORDERS_DATA;

---use of having clause
---write a query to find the country where only 1 order was placed.

SELECT country from orders_data group by country having count(*) =1;

---case when in sql

create table student_marks
(
    stu_id int,
    stu_name varchar(50),
    stu_marks int
);

insert into student_marks values(1,'tejas',50);
insert into student_marks values(2,'rahul',91);
insert into student_marks values(3,'amit',74);
insert into student_marks values(4,'nikhil',65);
insert into student_marks values(5,'rohit',86);
insert into student_marks values(6,'dipak',77);

----write a query to calculate the grades student by following  below criteria
---marks >=90,grade A+
---marks <90 and marks >=85,grade A
---marks <85 and marks >=75,grade B+
---marks <75 and marks >=60,grade B
---marks <60, grade C 

select * from student_marks;

select stu_id,
       stu_name,
       stu_marks,
       case
            when stu_marks >=90 then 'A+'
            when stu_marks >=85 and stu_marks <90 then 'A'
            when stu_marks >=75 and stu_marks <85 then 'B+'
            when stu_marks >=60 and stu_marks <75 then 'B'
            else 'c'
            end as grade
from student_marks;





