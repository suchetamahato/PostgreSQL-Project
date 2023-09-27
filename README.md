# DIGITAL MUSIC STORE DATA ANALYSIS USING POSTGRESQL

In this project, I used SQL queries to analyze a digital music store's data. I did various tasks like finding the most experienced employees, figuring out the top customers, and discovering popular music genres in different countries. For example, I found the most senior employee based on their job title and identified countries with the most invoices. I also determined the top 3 invoice values and which city had the best customers. Additionally, I identified the best-spending customer. To do all this, I wrote specific SQL queries that provided valuable insights into the database.

# Questions and Answers

🔎 **Q1: Who is the senior most employee based on job title?** 

I found the most senior employee by retrieving their job title, last name, and first name from the "employee" table. I sorted the results by the "levels" column in descending order, assuming it indicates seniority, and limited the output to one row using LIMIT 1.

🔎 **Q2: Which countries have the most Invoices?**

To determine the countries with the most invoices, I counted the number of invoices for each billing country from the "invoice" table. I grouped the results by billing country and displayed them in descending order of invoice count.

🔎 **Q3: What are top 3 values of total invoice?**

I identified the top 3 highest invoice amounts by selecting the "total" column from the "invoice" table and sorting the results by "total" in descending order.

🔎 **Q4: Which city has the best customers? We would like to throw a promotional Music Festival in the city we made the most money. 
Write a query that returns one city that has the highest sum of invoice totals. 
Return both the city name & sum of all invoice totals.**

I evaluated which city had the best customers by calculating the sum of total invoice amounts for each billing city. I grouped the results by billing city, sorted them by the sum of invoice totals in descending order, and limited the result to one row.

🔎 **Q5: Who is the best customer? The customer who has spent the most money will be declared the best customer. 
Write a query that returns the person who has spent the most money.**

To find the customer who spent the most money, I joined the "customer" and "invoice" tables on the "customer_id" column. I calculated the total spending for each customer, sorted the results by total spending in descending order, and displayed the customer who spent the most money.

🔎 **Q6: Write query to return the email, first name, last name, & Genre of all Rock Music listeners. 
Return your list ordered alphabetically by email starting with A.**

I provided two methods to find this information. Both methods involved joining multiple tables like "customer," "invoice," "invoice_line," "track," and "genre." They filtered for tracks with the genre name "Rock" and retrieved customer details for those who purchased such tracks. The results were ordered alphabetically by email.

🔎 **Q7: Let's invite the artists who have written the most rock music in our dataset. 
Write a query that returns the Artist name and total track count of the top 10 rock bands.**

I identified the top 10 rock bands/artists based on the count of their rock songs. I joined the "track," "album," "artist," and "genre" tables to filter for rock songs. Then, I grouped the results by artist and counted the number of songs for each, selecting the top 10 artists based on the count of their rock songs.

🔎 **Q8: Return all the track names that have a song length longer than the average song length. 
Return the Name and Milliseconds for each track. Order by the song length with the longest songs listed first.**

I selected track names and their lengths (in milliseconds) for tracks longer than the average track length. To calculate the average track length, I used a subquery. The results were sorted by song length in descending order.

🔎 **Q9: Find how much amount spent by each customer on artists? Write a query to return customer name, artist name and total spent.**

I used a common table expression (CTE) named "best_selling_artist" to find the artist who earned the most based on invoice line data. Then, I joined multiple tables in the main query to calculate how much each customer spent on the best-selling artist. The results were grouped by customer and artist, and the total spending was ordered in descending order.

🔎 **Q10: We want to find out the most popular music Genre for each country. We determine the most popular genre as the genre 
with the highest amount of purchases. Write a query that returns each country along with the top Genre. For countries where 
the maximum number of purchases is shared return all Genres.**

I provided two methods, one using a CTE and another using a recursive CTE, to calculate the most popular genre for each country based on the number of purchases. The results showed only the top genre(s) for each country.

🔎 **Q11: Write a query that determines the customer that has spent the most on music for each country. 
Write a query that returns the country along with the top customer and how much they spent. 
For countries where the top amount spent is shared, provide all customers who spent this amount.**

I presented two methods, one using a CTE and another using a recursive CTE, to determine the customer who spent the most on music for each country. The results displayed the top-spending customer(s) for each country.
