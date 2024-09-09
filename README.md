# Business Analytics with SQL and Python
## Overview
This project aims to answer key business questions by retrieving data from a database using SQL queries, processing the data in Python, and visualizing the results through various plots. The project demonstrates how data analytics can be utilized to derive valuable insights for decision-making.

## Features
- SQL Queries: Execute complex SQL queries to extract relevant data from a relational database.
- Data Processing: Use Python libraries such as pandas and numpy to clean, transform, and analyze the data.
- Visualization: Create insightful visualizations using matplotlib and seaborn to present the findings effectively.
- Business Insights: Answer specific business questions with data-driven approaches.
  
## Technologies Used
- Python: For scripting and data analysis.
- SQL: For data retrieval and manipulation.
- Pandas: For data manipulation and analysis.
- Matplotlib: For data visualization.
- Seaborn: For enhanced visualizations.
- Jupyter Notebook: For an interactive data analysis environment.

## Graphs Examples
### What countries do most of our sales come from?

```
df = getData('''select country.country, count(customer.customer_id) as country_count from country
inner join city
on city.country_id = country.country_id
inner join address
on address.city_id = city.city_id
inner join customer
on address.address_id = customer.address_id
group by country.country
order by country_count desc
limit 5;''')
```

![image](https://github.com/user-attachments/assets/9b28778c-eecf-4ee7-a18e-24c91f95d8f5)

### What is the average length of the films?

```
df = getData('''select length from film
order by length;''')
mean = getData('''select avg(length) from film;''').iloc[0,0]
```

![image](https://github.com/user-attachments/assets/553a9ea0-b3a4-4908-b8a3-a23753f9dac1)

### Who is the most common actor in the films?

```
df = getData('''select actor.last_name, count(actor.last_name) as actor_count from actor
inner join film_actor
on film_actor.actor_id = actor.actor_id
inner join film
on film.film_id = film_actor.actor_id
group by actor.last_name
order by actor_count desc
limit 5;''')
```
![image](https://github.com/user-attachments/assets/1fb8e92a-3fa3-480d-aa5b-c79f88e9476b)



If you have any questions or suggestions, please feel free to reach out at davidotero856@gmail.com.
