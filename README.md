# DIGITAL MUSIC STORE DATA ANALYSIS USING POSTGRESQL

In this project, I wrote a series of SQL queries to analyze a database, addressing various questions and tasks ranging from identifying senior employees to determining the top customers and popular music genres by country.

# Questions and Answers

🔎**Q1: Who is the senior most employee based on job title?** 

The query retrieves the job title, last name, and first name of employees from the "employee" table. It orders the results by the "levels" column in descending order, assuming that "levels" represents seniority. It limits the result to one row using `LIMIT 1`, thus giving the most senior employee based on job title.

🔸**Q2: Which countries have the most Invoices?**

The query counts the number of invoices for each billing country from the "invoice" table. It groups the results by billing country. It orders the results by the count of invoices in descending order, showing countries with the most invoices first.

🔸**Q3: What are the top 3 values of total invoice?**

The query selects the "total" column from the "invoice" table. It orders the results by the "total" column in descending order, giving the highest total invoices first.

🔸**Q4: Which city has the best customers?**

The query calculates the sum of total invoice amounts for each billing city. It groups the results by billing city. It orders the results by the sum of invoice totals in descending order. It limits the result to one row, giving the city with the highest sum of invoice totals.

🔸**Q5: Who is the best customer?**

The query identifies the customer who has spent the most money. It joins the "customer" and "invoice" tables on the "customer_id" column. It calculates the sum of total spending for each customer. It orders the results by total spending in descending order. It limits the result to one row, giving the customer who has spent the most money.

🔸**Q6: Write a query to return the email, first name, last name, & Genre of all Rock Music listeners.**

Two methods are provided to achieve the same result. Both methods involve joining multiple tables: "customer," "invoice," "invoiceline," "track," and "genre". They filter for tracks with a genre name "Rock" and retrieve customer details for those who have purchased such tracks. The results are ordered alphabetically by email.

🔸**Q7: Let's invite the artists who have written the most rock music.**

The query identifies the top 10 rock bands/artists based on the count of their rock songs. It joins the "track," "album," "artist," and "genre" tables to filter for rock songs. It groups the results by artist and counts the number of songs for each. The top 10 artists are selected based on the count of their rock songs.

🔸**Q8: Return all the track names that have a song length longer than the average song length.**

The query selects track names and song lengths (in milliseconds) for tracks with lengths greater than the average track length. It calculates the average track length using a subquery. The results are ordered by song length in descending order.

🔸**Q9: Find how much amount spent by each customer on artists?**

A common table expression (CTE) named "best_selling_artist" is defined to find the artist who earned the most based on invoice line data. The main query then joins multiple tables to calculate how much each customer spent on the best-selling artist. It groups the results by customer and artist, summing the total spending, and orders them by the amount spent in descending order.

🔸**Q10: We want to find out the most popular music Genre for each country.**

Two methods are provided, one using a CTE and another using a recursive CTE. Both methods calculate the most popular genre for each country based on the number of purchases. The results are filtered to show only the top genre(s) for each country.

🔸**Q11: Write a query that determines the customer that has spent the most on music for each country.**

Two methods are provided, one using a CTE and another using a recursive CTE. Both methods calculate the customer who spent the most on music for each country. The results are filtered to show the top-spending customer(s) for each country.

