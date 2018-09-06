# session27--Assignment27_1-Assignment1
DATA ANALYTICS WITH R, EXCEL AND TABLEAU SESSION 26 ASSIGNMENT 1




SESSION 11: RDBMS (CONTD.)
Assignment 1
Assignment 27_1

4. Associated Data Files Use the Sakila schema, which can be found in following link (to be installed in your local system) 
http://dev.mysql.com/doc/index-other.html("sakila database") 
http://dev.mysql.com/doc/sakila/en/sakila.html(for full documentation) Requirements 
For each question, you are required to provide the following: 
- The SQL query you used 
- The answers 
- Any assumptions you made 
5. Problem Statement
 1. Return the categories (names) of the longest film. NOTE that there may be several "longest" films (i.e. with the same length), so you might need to return more than one category. Return the duration as well.  
2.  Find the movies whose total number of actors is above the average. Return the movie names and its number of actors ordered by the title. IMPORTANT NOTE: this query should return many movies. Please write in your submission only the first TOP-10 results.



Answers:-
27.1.1
Question: Return the categories (names) of the longest film. NOTE that there may be several "longest" films (i.e. with the same length), so you might need to return more than one category. Return the duration as well.

Select category.name,rental_duration,max(length) from film join film_category using (film_id) join category using (category_id) group by category.name having max(length)=(select max(length) from film);
========================
27.1.2
Question: Find the movies whose total number of actors is above the average. Return the movie names and its number of actors ordered by the title. IMPORTANT NOTE: this query should return many movies. Please write in your submission only the first TOP-10 results.

Select title,count(actor_id) from film f inner join film_actor fa on f.film_id=fa.film_id group by title having count(actor_id)>10 limit 10;
(assumed average actors/film=10).




 
