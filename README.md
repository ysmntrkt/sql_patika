# sql_patika
ödev
soru 1 
SELECT title,description FROM film
soru 2
SELECT title,description FROM film WHERE length > 60 AND length < 75;  
soru 3
SELECT title,description FROM film WHERE rental_rate =0.99 AND  replacement_cost = 12.99 OR  replacement_cost = 28.99;
soru 4
SELECT first_name,last_name FROM customer WHERE first_name = 'Mary'
soru 5
SELECT * FROM film WHERE NOT length > 50 AND  rental_rate = 2.99 OR  rental_rate = 4.99; 
