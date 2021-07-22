# MySQL - Basics

## Table


First Name | City | Age
------------ | -------------
Sandy | Los Angeles | 27
Ron | Miami | 34

 ## SELECT 

```sql
SELECT * FROM flights;
```

```sql
SELECT origin, destination FROM flights;
```

```sql
SELECT * FROM flights WHERE id = 3;
```

```sql
SELECT * FROM flights WHERE origin = "New York";
```

```sql
SELECT * FROM flights WHERE duration > 500;
```

## UPDATE

```sql
UPADTE flights
  SET duration = 439
  WHERE origin = "New York"
  AND destination = "London";
```

## DELETE

```sql
DELETE FROM flights WHERE destination = "Tokyo";
```




![Image of cat](https://pinklillies.github.io/images/cat.jfif)
