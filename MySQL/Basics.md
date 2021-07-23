# MySQL - Basics



## run cmd 

```
sqlite3

```

**Table : candidates**

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
UPDATE candidates
  SET age = 43
  WHERE city = "New York"
  AND name = "Bianca";
```

## DELETE

```sql
DELETE FROM candidates WHERE city = "Los Angeles";
```

## JOIN

```sql
SELECT first, origin, destination
FROM flights JOIN passengers
ON passengers.flight_id = fligts.id;
```

The flight_id of the table passengers 
and 
the id of the flights table


## CREATE INDEX

```sql
CREATE INDEX name_index ON passengers (last);
```


create an index on the table passengers



## Add a comment

```sql
"--"
```





![cat6](https://pinklillies.github.io/images/cat6.jfif)


