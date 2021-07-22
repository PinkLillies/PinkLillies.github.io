# MySQL - Basics

**Table : candidates

|id   | Name       | City         | Age |
|-----|------------|--------------|-----|
|1    |Sandy       | Los Angeles  | 27  |
|2    |Ron         | Miami        | 34  |
|3    |Brad        | Miami        | 28  | 
|4    |Jennifer    | New York     | 28  | 

## SELECT 

```sql
SELECT * FROM candidates;
```

```sql
SELECT Name, City FROM candidates;
```

```sql
SELECT * FROM candidates WHERE id = 3;
```

```sql
SELECT * FROM candidates WHERE city = "Miami";
```

```sql
SELECT * FROM candidates WHERE age > 30;
```

## UPDATE

```sql
UPADTE candidates
  SET age = 43
  WHERE city = "New York"
  AND name = "Bianca";
```

## DELETE

```sql
DELETE FROM candidates WHERE city = "Los Angeles";
```




![Image of cat](https://pinklillies.github.io/images/cat.jfif)
