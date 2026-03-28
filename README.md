# Netflix-sql-analytics-project
🎬 Netflix SQL Data Analysis Project This project focuses on analyzing Netflix dataset using SQL to extract meaningful insights about content trends, genres, ratings, and release patterns. It demonstrates strong skills in data querying, data cleaning, and analytical thinking using real-world data.

<img width="1200" height="500" alt="netflix_banner_resized" src="https://github.com/user-attachments/assets/b956dbcb-0ee6-4c35-9d3d-14d4ac1f80be" />

## 📊 Business Problems & Solutions (SQL Analysis)

This project solves real-world business questions using SQL on Netflix dataset.

---

### 🔍 Problem Statements

#### 1️⃣ Count Movies vs TV Shows

```sql
SELECT type, COUNT(*) AS total_count
FROM netflix
GROUP BY type;
```

---

#### 2️⃣ Most Common Rating

```sql
SELECT type, rating, COUNT(*) AS count
FROM netflix
GROUP BY type, rating
ORDER BY count DESC;
```

---

#### 3️⃣ Movies Released in 2020

```sql
SELECT title
FROM netflix
WHERE type = 'Movie' AND release_year = 2020;
```

---

#### 4️⃣ Top 5 Countries with Most Content

```sql
SELECT country, COUNT(*) AS total
FROM netflix
GROUP BY country
ORDER BY total DESC
LIMIT 5;
```

---

#### 5️⃣ Longest Movie

```sql
SELECT title, duration
FROM netflix
WHERE type = 'Movie'
ORDER BY duration DESC
LIMIT 1;
```

---

#### 6️⃣ Content Added in Last 5 Years

```sql
SELECT *
FROM netflix
WHERE date_added >= CURRENT_DATE - INTERVAL '5 years';
```

---

#### 7️⃣ Content by Director 'Rajiv Chilaka'

```sql
SELECT *
FROM netflix
WHERE director = 'Rajiv Chilaka';
```

---

#### 8️⃣ TV Shows with More Than 5 Seasons

```sql
SELECT title, duration
FROM netflix
WHERE type = 'TV Show'
AND duration LIKE '%Season%'
AND CAST(SPLIT_PART(duration, ' ', 1) AS INT) > 5;
```

---

#### 9️⃣ Content Count by Genre

```sql
SELECT listed_in AS genre, COUNT(*) AS total
FROM netflix
GROUP BY listed_in;
```

---

#### 🔟 Top 5 Years with Highest Avg Content Release in India

```sql
SELECT release_year, COUNT(*) AS avg_content
FROM netflix
WHERE country = 'India'
GROUP BY release_year
ORDER BY avg_content DESC
LIMIT 5;
```

---

#### 1️⃣1️⃣ Documentary Movies

```sql
SELECT title
FROM netflix
WHERE type = 'Movie'
AND listed_in LIKE '%Documentaries%';
```

---

#### 1️⃣2️⃣ Content Without Director

```sql
SELECT *
FROM netflix
WHERE director IS NULL OR director = '';
```

---

#### 1️⃣3️⃣ Salman Khan Movies in Last 10 Years

```sql
SELECT COUNT(*) AS total_movies
FROM netflix
WHERE casts LIKE '%Salman Khan%'
AND release_year >= EXTRACT(YEAR FROM CURRENT_DATE) - 10;
```

---

#### 1️⃣4️⃣ Top 10 Actors in Indian Movies

```sql
SELECT casts, COUNT(*) AS movie_count
FROM netflix
WHERE country = 'India'
GROUP BY casts
ORDER BY movie_count DESC
LIMIT 10;
```

---

#### 1️⃣5️⃣ Content Categorization (Good vs Bad)

```sql
SELECT 
  CASE 
    WHEN description ILIKE '%kill%' OR description ILIKE '%violence%' 
    THEN 'Bad'
    ELSE 'Good'
  END AS category,
  COUNT(*) AS total
FROM netflix
GROUP BY category;
```

---

## 📌 Conclusion

This SQL project demonstrates strong skills in:

* Data querying
* Data cleaning
* Business analysis
* Real-world problem solving

---
