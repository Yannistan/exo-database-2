ex2:

SELECT title, description FROM film WHERE DESCRIPTION LIKE '%Amazing%';

ex3:

SELECT customer.customer_id, customer.first_name, customer.last_name, payment.amount, payment.payment_date FROM customer INNER JOIN payment ON customer.customer_id = payment.customer_id WHERE payment.amount > 10;

ex4:

SELECT SUM (amount) AS total FROM payment;

ex5:

SELECT title FROM film INNER JOIN language ON film.language_id = language.language_id WHERE language.name = 'English' AND film.length > 120;

ex6:

WITH total_data AS ( SELECT customer_id, SUM(amount) FROM payment GROUP BY customer_id) SELECT customer.customer_id, first_name, last_name, email, sum FROM total_data INNER JOIN customer ON total_data.customer_id = customer.customer_id ORDER BY sum DESC LIMIT 10;

ex7:

SELECT customer_id , SUM (amount) AS total FROM payment GROUP BY customer_id ORDER BY total DESC LIMIT 10;

ex8:
