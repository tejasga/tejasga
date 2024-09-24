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





