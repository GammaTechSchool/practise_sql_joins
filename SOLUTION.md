# Soluciones de los ejercicios

## Ejercicio 1
SELECT SUM(quantity), color AS total_ammount 
FROM bills 
INNER JOIN shirts 
ON product_id = shirts.id 
WHERE product_id = shirts.id
GROUP BY color;
## Ejercicio 2
SELECT SUM(quantity), color AS total_ammount, 
SUM(shirts.price)  AS total_sales 
FROM bills INNER JOIN shirts 
ON product_id = shirts.id 
WHERE product_id = shirts.id 
GROUP BY color;
## Ejercicio 3
SELECT dealers.name, 
SUM(quantity) AS total_ammount 
FROM bills 
INNER JOIN dealers
ON dealer_id = dealers.id 
WHERE product_id = dealers.id 
GROUP BY dealers.name;
## Ejercicio 4
SELECT dealers.name, SUM(quantity) AS total_ammount, 
SUM(price) FROM bills 
INNER JOIN dealers
ON dealer_id = dealers.id 
INNER JOIN shirts
ON shirts.id = product_id
WHERE product_id = dealers.id 
GROUP BY dealers.name;
## Ejercicio 5
SELECT shirts.color, SUM(quantity) AS total_ammount
FROM bills 
INNER JOIN dealers
ON dealer_id = dealers.id 
INNER JOIN shirts
ON shirts.id = product_id
WHERE dealers.id = 1
GROUP BY shirts.color;
## Ejercicio 6
SELECT departments.name, SUM(quantity) AS total_ammount, 
SUM(price) AS total_sales
FROM bills 
INNER JOIN shirts
ON shirts.id = product_id
INNER JOIN dealers
ON dealers.id = dealer_id
INNER JOIN departments
ON department_id = departments.id 
WHERE dealers.id = dealer_id AND department_id = departments.id
GROUP BY departments.name;
## Ejercicio 7
SELECT SUM(quantity) AS total_ammount 
FROM bills 
WHERE date >= '01-06-2023' AND date <= '15-06-2023';
## Ejercicio 8
SELECT color, SUM(quantity) AS total_ammount 
FROM bills 
INNER JOIN shirts
ON product_id = shirts.id
WHERE date >= '2023-06-20' AND date <= '2023-06-30'
GROUP BY color
## Ejercicio 9
SELECT departments.name, SUM(quantity) AS total_ammount, 
SUM(price) AS total_sales
FROM bills 
INNER JOIN shirts
ON shirts.id = product_id
INNER JOIN dealers
ON dealers.id = dealer_id
INNER JOIN departments
ON department_id = departments.id 
WHERE dealers.id = dealer_id AND department_id = departments.id AND departments.id = 1
GROUP BY departments.name;
## Ejercicio 10
SELECT departments.name, COUNT(quantity) AS total_tickets, 
SUM(price) AS total_sales
FROM bills 
INNER JOIN shirts
ON shirts.id = product_id
INNER JOIN dealers
ON dealers.id = dealer_id
INNER JOIN departments
ON department_id = departments.id 
WHERE dealers.id = dealer_id AND department_id = departments.id AND departments.id = 2
GROUP BY departments.name;