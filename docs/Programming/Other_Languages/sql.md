# SQL

### Data type
1. INTEGER
2. REAL
3. TEXT
4. CHAR
5. VARCHAR
6. DATE

### Constraints
1. PRIMARY KEY
2. UNIQUE
3. NOT NULL
4. DEFAULT
5. FOREIGN KEY, 
6. CHECK
7. INDEX

> Clause is the command such as `CREATE`,`FROM`
### Manipulation
```sql
CREATE TABLE table_name (   
	id INTEGER,
	name TEXT,
	age INTEGER
)

INSERT INTO table (id, name, age) 
VALUES (1, 'Justin Bieber', 29);

SELECT name FROM celebs;
SELECT * FROM celebs;

ALTER TABLE celebs
ADD COLUMN twitter_handle TEXT;

UPDATE celebs
SET twitter_hand le = "@taylorswift13"
WHERE id = 4;

DELETE FROM celebs
WHERE twitter_handle IS NULL;

AS

LIKE

BETWEEN

OR

ORDER BY

LIMIT


CASE
	WHEN xx THEN
	ELSE xx
END

COUNT

SUM

MAX/MIN

AVERAGE

ROUND

GROUP BY

HAVING
```
