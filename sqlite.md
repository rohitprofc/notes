# SQLite - A RDBMS that uses SQL as its query language

## Installing SQLite

- Goto [SQLite Download Page](https://www.sqlite.org/download.html)
- Download **DLL** and Shell **ZIP** files
- Create `sqlite` folder in `C:`
- Extract the downloaded ZIP files in `C:/sqlite`
- Add `C:/sqlite` path in **environment variables**

## Using SQLite

- Open terminal
- create a file `FILE_NAME.sql`
- command for creating file in windows `type NUL > FILE_NAME.sql`
- now open the created file using `sqlite FILE_NAME.sql`
- Succesfully opened the **FILE_NAME.sql** file using **SQLite3**

## SQLite Data types

- TEXT
- NUMERIC (Bool or Date)
- INTEGER
- REAL (Real numbers)
- BLOB (Image, Audio, Video)

## SQLite Constraints

- CHECK
- DEFAULT
- NOT NULL
- PRIMARY KEY
- UNIQUE

## SQLite Functions
- AVERAGE
- COUNT
- MAX
- MIN
- SUM

## SQLite Clauses
- LIMIT
- ORDER BY
- GROUP BY
- HAVING

## SQLite commands

| SNo | Action            | Command              |
|----:|:------------------|:---------------------|
|   1 | Clear output      | `.shell cls`         |
|   2 | Quit from SQLite  | `.quit`              |
|   3 | Show all tables   | `.tables`            |
|   4 | Table description | `.schema table_name` |
|   5 | Column mode       | `.mode columns`      |
|   6 | Column header ON  | `.header on`         |
|   7 | Column header OFF | `.header off`        |

## Creating Tables

```
CREATE TABLE table_name (
    column_name1 column_type constaint1 constaint2...,
    column_name2 column_type constaint1 constaint2...,
    .........
    column_name(n) column_type constaint1 constaint2...
);
```

## Inserting Data

```
Syntax 1:
INSERT INTO table_name (column_name1, column_name2, ....) 
                VALUES ('value_1', 'value_3'...);

Syntax 2:
INSERT INTO table_name VALUES ('value_1', 'value_3'...);
```

> **Note:** <br>
> Every string literal in values should be enclosed in single quotes only `''` it should not use `""`

## Retrieving Data

```
Syntax 1:
    SELECT * FROM table_name;

Syntax 2:
    SELECT column_name1, column_name2... FROM table_name;
```

### Using WHERE in Retreiving Data

```
For INTEGER data column:
    SELECT * FROM table_name WHERE column_name = value;
    SELECT * FROM table_name WHERE column_name > value;
    SELECT * FROM table_name WHERE column_name < value;

For TEXT data column:
    SELECT * FROM table_name WHERE column_name < "value";
```

### Other conditions used with WHERE

```
AND:
    SELECT * FROM table_name WHERE column_name1 = value AND column_name2 = value;

OR:
    SELECT * FROM table_name WHERE column_name1 = value OR column_name2 = value;

IN:
    SELECT * FROM table_name WHERE column_name IN ("value1, value2");

LIKE:
    SELECT * FROM table_name WHERE column_name LIKE "%value%";
```
## Update Data

```
UPDATE table_name
    SET column_name = new_value
    WHERE column_name = value
    AND column_name = value;
```
> Condition 2 is optional here

## Delete Data

```
DELETE from table_name 
    WHERE column_name = value;
```


## Other RDBM Systems

- MySQL
- PostgreSQL (Postgres)
- SQLite
