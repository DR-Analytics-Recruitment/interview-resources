Answers available from Douglas Robertson


Beginner:
Retrieve Data:

Question: Retrieve the names of all products in the Northwind products table.
sql
Copy code
SELECT ProductName FROM Products;
Question: List all artists from the Chinook database.
sql
Copy code
SELECT Name FROM Artists;
Filtering Data:

Question: Find all orders in Northwind shipped to Germany.
sql
Copy code
SELECT OrderID FROM Orders WHERE ShipCountry = 'Germany';
Question: Find tracks in Chinook that are longer than 5 minutes.
sql
Copy code
SELECT TrackName FROM Tracks WHERE Milliseconds > 300000;
Simple Joins:

Question: In Northwind, list orders along with their corresponding customer names.

sql
Copy code
SELECT OrderID, Customers.CompanyName 
FROM Orders 
JOIN Customers ON Orders.CustomerID = Customers.CustomerID;
Question: In Chinook, display each invoice along with the associated customer's first and last name.

sql
Copy code
SELECT InvoiceID, FirstName, LastName 
FROM Invoices 
JOIN Customers ON Invoices.CustomerID = Customers.CustomerID;
Aggregation:

Question: Calculate the average price of all products in Northwind.
sql
Copy code
SELECT AVG(UnitPrice) FROM Products;
Intermediate:
Complex Joins:

Question: In Sakila, find movies with actor 'Johnny Depp' and list both the movie and actor names.

sql
Copy code
SELECT title, first_name, last_name 
FROM film 
JOIN film_actor ON film.film_id = film_actor.film_id 
JOIN actor ON film_actor.actor_id = actor.actor_id 
WHERE first_name = 'Johnny' AND last_name = 'Depp';
Question: Join Northwind's orders, order details, and products to find the name of the top-selling product by quantity.

sql
Copy code
SELECT ProductName, SUM(Quantity) as TotalSold 
FROM OrderDetails 
JOIN Products ON OrderDetails.ProductID = Products.ProductID 
GROUP BY ProductName 
ORDER BY TotalSold DESC LIMIT 1;
Subqueries and Derived Tables:

Question: In Chinook, find the total invoice amount for customers who have purchased more than $50 in total.

sql
Copy code
SELECT CustomerID, SUM(Total) 
FROM Invoices 
GROUP BY CustomerID 
HAVING SUM(Total) > 50;
Question: Identify Northwind employees who have not made any sales.

sql
Copy code
SELECT EmployeeID, FirstName, LastName 
FROM Employees 
WHERE EmployeeID NOT IN (SELECT DISTINCT EmployeeID FROM Orders);
Advanced:
Window Functions:

Question: In Chinook, rank tracks in each album based on their length.

sql
Copy code
SELECT TrackName, AlbumId, 
       RANK() OVER (PARTITION BY AlbumId ORDER BY Milliseconds DESC) as Rank 
FROM Tracks;
Question: Calculate the cumulative sales for each Northwind product over time.

sql
Copy code
SELECT ProductID, OrderDate, 
       SUM(Quantity) OVER (PARTITION BY ProductID ORDER BY OrderDate) as CumulativeSales 
FROM Orders 
JOIN OrderDetails ON Orders.OrderID = OrderDetails.OrderID;
Complex Business Scenarios:

Question: Find the most popular category in Northwind based on product sales.
sql
Copy code
SELECT Categories.CategoryName, SUM(OrderDetails.Quantity) as TotalQuantity 
FROM Categories 
JOIN Products ON Categories.CategoryID = Products.CategoryID 
JOIN OrderDetails ON Products.ProductID = OrderDetails.ProductID 
GROUP BY Categories.CategoryName 
ORDER BY TotalQuantity DESC LIMIT 1;
This list can be expanded further based on specific areas of focus. Having a structured answer key and evaluation rubric can assist interviewers in assessing candidates uniformly.
