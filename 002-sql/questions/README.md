# SQL Interview Questions

---

## Beginner

### Retrieve Data:
- **Northwind**: List all categories from the _Categories_ table.
- **Chinook**: Retrieve the names of all albums.
- **Sakila**: Fetch the titles of the last 10 films added to the database.

### Filtering Data:
- **Northwind**: Find all products below a specific price point, say $20.
- **Chinook**: Find tracks that belong to the 'Jazz' genre.
- **Sakila**: List all films with a rental duration longer than 5 days.

### Simple Joins:
- **Northwind**: List all suppliers along with their corresponding contact names.
- **Chinook**: Fetch each playlist along with its track count.
- **Sakila**: Display the names of customers who have rented the film named "ACADEMY DINOSAUR".

### Aggregation:
- **Northwind**: How many products are there in each category?
- **Chinook**: What's the total duration (in minutes) of all tracks per album?
- **Sakila**: How many films are there in each film category?

---

## Intermediate

### Complex Joins:
- **Sakila**: List actors who have played in more than 30 films.
- **Northwind**: Which customers have placed more than 20 orders?
- **Chinook**: Identify albums with tracks belonging to multiple genres.

### Subqueries and Derived Tables:
- **Chinook**: What's the average track count for albums by artists with more than 5 albums?
- **Northwind**: Which employees have served customers from more than 5 different countries?
- **Sakila**: List films that have been rented by at least half of the customers.

### Date and Time Functions:
- **Northwind**: Which orders were placed in December 1997?
- **Chinook**: Find invoices raised in the first quarter of 2009.
- **Sakila**: List movies that were rented last weekend.

---

## Advanced

### Window Functions:
- **Chinook**: For each artist, rank albums based on their release date.
- **Northwind**: Calculate the monthly cumulative sales per product throughout 1997.
- **Sakila**: For each film category, rank movies based on their rental frequency.

### CTEs (Common Table Expressions):
- **Northwind**: Find the monthly sales trend for the year 1997.
- **Chinook**: Identify top genres in terms of total track duration.
- **Sakila**: Using CTEs, recursively find all staff members managed by a particular manager.

### Complex Business Scenarios:
- **Northwind**: Identify the best-selling product in each category for the year 1997.
- **Chinook**: Which artists have the highest revenue generation across all their albums?
- **Sakila**: Determine the most popular film category in each city based on rental counts.

---

> **Note**: Use these questions to assess SQL proficiency. Evaluate candidates based on the accuracy, efficiency, and clarity of their answers.
