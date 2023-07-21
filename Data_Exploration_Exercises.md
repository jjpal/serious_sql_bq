### Data Exploration Exercises On BigQuery - Answering Business Questions

1] Which customer_id had the latest rental_date for inventory_id = 1 and 2?

```sql
SELECT
  customer_id,
  inventory_id,
  rental_date
FROM dvd_rentals.rental
WHERE inventory_id = 1 OR inventory_id = 2
ORDER BY inventory_id, rental_date DESC
LIMIT 10;
```

2] Which category has the highest total_sales?
```sql
SELECT
   category,
   total_sales
FROM dvd_rentals.sales_by_film_category
ORDER BY total_sales DESC
LIMIT 5;
```

3] What is the name of the category with the highest category_id in the dvd_rentals.category table?
```sql
SELECT
  name,
  category_id
FROM dvd_rentals.category
ORDER BY category_id DESC
```

4] For the films with the longest length, what is the title of the “R” rated film with the lowest 
replacement_cost in dvd_rentals.film table?
```sql
SELECT 
    title,
    replacement_cost,
    length,
    rating  
FROM dvd_rentals.film
WHERE rating = 'R' 
ORDER BY length DESC, replacement_cost ASC
LIMIT 5;
```

5] Who was the manager of the store with the highest total_sales in the dvd_rentals.sales_by_store table?
```sql
SELECT 
    manager, 
    total_sales
FROM dvd_rentals.sales_by_store
ORDER BY total_sales DESC
LIMIT 1;
```

6] What is the postal_code of the city with the 5th highest city_id in the dvd_rentals.address table?
```sql
SELECT
     postal_code,
     city_id
FROM dvd_rentals.address
ORDER BY city_id DESC
LIMIT 5;
```

