# SQL Interview Questions with Answers

---

### Retrieve Data:
- **Northwind**: List all categories from the _Categories_ table.

`SELECT CategoryName FROM Categories;`


- **Chinook**: Retrieve the names of all albums.
- **Sakila**: Fetch the titles of the last 10 films added to the database.


Chinook: Retrieve the names of all albums.
SELECT Title FROM Albums;

Sakila: Fetch the titles of the last 10 films added to the database.
SELECT title FROM film ORDER BY film_id DESC LIMIT 10;

Filtering Data
Northwind: Find all products below a specific price point, say $20.
SELECT ProductName, UnitPrice FROM Products WHERE UnitPrice < 20;

Chinook: Find tracks that belong to the 'Jazz' genre.
SELECT TrackName FROM Tracks WHERE GenreId IN (SELECT GenreId FROM Genres WHERE Name = 'Jazz');

Sakila: List all films with a rental duration longer than 5 days.
SELECT title FROM film WHERE rental_duration > 5;

Simple Joins
Northwind: List all suppliers along with their corresponding contact names.
SELECT CompanyName, ContactName FROM Suppliers;

Chinook: Fetch each playlist along with its track count.
SELECT PlaylistId, COUNT(TrackId) AS TrackCount FROM PlaylistTrack GROUP BY PlaylistId;

Sakila: Display the names of customers who have rented the film named "ACADEMY DINOSAUR".
SELECT c.first_name, c.last_name FROM customer c JOIN rental r ON c.customer_id = r.customer_id JOIN inventory i ON r.inventory_id = i.inventory_id JOIN film f ON i.film_id = f.film_id WHERE f.title = 'ACADEMY DINOSAUR';

Aggregation
Northwind: How many products are there in each category?
SELECT CategoryID, COUNT(ProductID) AS NumberOfProducts FROM Products GROUP BY CategoryID;

Chinook: What's the total duration (in minutes) of all tracks per album?
SELECT AlbumId, SUM(Milliseconds)/60000 AS TotalMinutes FROM Tracks GROUP BY AlbumId;

Sakila: How many films are there in each film category?
SELECT category_id, COUNT(film_id) AS NumberOfFilms FROM film_category GROUP BY category_id;

Intermediate
Complex Joins
Sakila: List actors who have played in more than 30 films.
SELECT a.first_name, a.last_name FROM actor a JOIN film_actor fa ON a.actor_id = fa.actor_id GROUP BY a.actor_id, a.first_name, a.last_name HAVING COUNT(fa.film_id) > 30;

Northwind: Which customers have placed more than 20 orders?
SELECT CustomerID, COUNT(OrderID) AS OrderCount FROM Orders GROUP BY CustomerID HAVING OrderCount > 20;

Chinook: Identify albums with tracks belonging to multiple genres.
SELECT AlbumId, COUNT(DISTINCT GenreId) AS GenresCount FROM Tracks GROUP BY AlbumId HAVING GenresCount > 1;

Subqueries and Derived Tables
Chinook: What's the average track count for albums by artists with more than 5 albums?
SELECT AVG(TrackCount) FROM (SELECT AlbumId, COUNT(TrackId) AS TrackCount FROM Tracks GROUP BY AlbumId) sub1 WHERE ArtistId IN (SELECT ArtistId FROM Albums GROUP BY ArtistId HAVING COUNT(AlbumId) > 5);

Northwind: Which employees have served customers from more than 5 different countries?
SELECT EmployeeID FROM Orders JOIN Customers ON Orders.CustomerID = Customers.CustomerID GROUP BY EmployeeID HAVING COUNT(DISTINCT Customers.Country) > 5;

Sakila: List films that have been rented by at least half of the customers.
SELECT film_id, title FROM film WHERE film_id IN (SELECT inventory.film_id FROM rental JOIN inventory ON rental.inventory_id = inventory.inventory_id GROUP BY inventory.film_id HAVING COUNT(DISTINCT rental.customer_id) >= (SELECT COUNT(*)/2 FROM customer));

Date and Time Functions
Northwind: Which orders were placed in December 1997?
SELECT OrderID FROM Orders WHERE OrderDate BETWEEN '1997-12-01' AND '1997-12-31';

Chinook: Find invoices raised in the first quarter of 2009.
SELECT InvoiceId FROM Invoices WHERE InvoiceDate BETWEEN '2009-01-01' AND '2009-03-31';

Sakila: List movies that were rented last weekend.
(Note: This requires knowledge of the exact date range considered as "last weekend". Example provided for a hypothetical date.)
SELECT film.title FROM film JOIN inventory ON film.film_id = inventory.film_id JOIN rental ON inventory.inventory_id = rental.inventory_id WHERE rental.rental_date BETWEEN 'YYYY-MM-DD' AND 'YYYY-MM-DD';

Advanced
Window Functions
Chinook: For each artist, rank albums based on their release date.
(Note: Assuming a column named ReleaseDate exists in the Albums table, which it doesn't in the original schema.)
SELECT ArtistId, AlbumId, RANK() OVER(PARTITION BY ArtistId ORDER BY ReleaseDate) AS AlbumRank FROM Albums;

Northwind: Calculate the monthly cumulative sales per product throughout 1997.
SELECT ProductID, MONTH(OrderDate) AS Month, SUM(UnitPrice * Quantity) AS CumulativeMonthlySales FROM Orders JOIN OrderDetails ON Orders.OrderID = OrderDetails.OrderID WHERE YEAR(OrderDate) = 1997 GROUP BY ProductID, MONTH(OrderDate);

Sakila: For each film category, rank movies based on their rental frequency.
SELECT category_id, film_id, RANK() OVER(PARTITION BY category_id ORDER BY COUNT(rental_id) DESC) AS FilmRank FROM film JOIN film_category ON film.film_id = film_category.film_id JOIN inventory ON film.film_id = inventory.film_id JOIN rental ON inventory.inventory_id = rental.inventory_id GROUP BY category_id, film_id;

CTEs (Common Table Expressions)
Northwind: Find the monthly sales trend for the year 1997.
WITH MonthlySales AS ( SELECT MONTH(OrderDate) AS Month, SUM(UnitPrice * Quantity) AS TotalSales FROM Orders JOIN OrderDetails ON Orders.OrderID = OrderDetails.OrderID WHERE YEAR(OrderDate) = 1997 GROUP BY MONTH(OrderDate) ) SELECT Month, TotalSales FROM MonthlySales ORDER BY Month;

Chinook: Identify top genres in terms of total track duration.
WITH GenreDuration AS ( SELECT GenreId, SUM(Milliseconds) AS TotalDuration FROM Tracks GROUP BY GenreId ) SELECT Genres.Name, TotalDuration FROM GenreDuration JOIN Genres ON GenreDuration.GenreId = Genres.GenreId ORDER BY TotalDuration DESC LIMIT 5;

Sakila: Using CTEs, recursively find all staff members managed by a particular manager.
(Note: This assumes a hierarchical structure in the staff table, which isn't present in the original Sakila schema. Hypothetical structure provided for the
