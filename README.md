SELECT DISTINCT country FROM customers

SELECT * FROM customers

SELECT * FROM customers WHERE 

SELECT * FROM customers WHERE customer_id LIKE '%BL%'

SELECT * FROM orders LIMIT 100;

SELECT * FROM customers WHERE postal_code IN ('1010', '3012', '12209', '05023');

SELECT * FROM orders WHERE ship_region IS NOT NULL;

SELECT * FROM customers ORDER BY country, city;

INSERT INTO customers (customer_id, company_name, contact_name, city, phone)
VALUES ('1', 'John', 'Amazon', 'Detroit', '2488752419');

UPDATE orders SET ship_region = 'EuroZone' WHERE ship_country = 'France';

DELETE FROM order_details WHERE quantity = '1';

SELECT AVG(quantity) AS avg_quantity, MAX(quantity) AS max_quantity, MIN(quantity) AS min_quantity
FROM order_details;

SELECT order_id, AVG(quantity) AS avg_quantity, MAX(quantity) AS max_quantity, MIN(quantity) AS min_quantity
FROM order_details GROUP BY order_id;

SELECT customer_id FROM orders WHERE order_id = 10290;

SELECT * From orders INNER JOIN customers ON orders.customer_id = customers.customer_id;

SELECT * FROM orders LEFT JOIN customers ON orders.customer_id = customers.customer_id;

SELECT * FROM orders RIGHT JOIN customers ON orders.customer_id = customers.customer_id;

SELECT orders.ship_city, orders.ship_country FROM orders 
INNER JOIN employees ON employees.employee_id = orders.employee_id 
WHERE city = 'London'

SELECT DISTINCT orders.ship_name
FROM orders
JOIN order_details ON orders.order_id = order_details.order_id
JOIN products ON order_details.product_id = products.product_id
WHERE products.discontinued = 1;

SELECT employees.first_name
FROM employees
LEFT JOIN employees supervisor ON employees.reports_to = supervisor.employee_id
WHERE supervisor.employee_id IS NULL;
