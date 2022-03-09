# useful gists

To save you time from writing/researching boilerplate SQL/python, here is a useful collection of things for quick reference:

### SQL statements

```sql
-- Example create table statement
CREATE TABLE swapi_people(
   id         INTEGER NOT NULL PRIMARY KEY,
   name       TEXT 	  NOT NULL,
   height     TEXT 	  NOT NULL,
   mass       TEXT 	  NOT NULL,
   hair_color TEXT 	  NOT NULL,
   skin_color TEXT 	  NOT NULL,
   eye_color  TEXT 	  NOT NULL,
   birth_year TEXT 	  NOT NULL,
   gender     TEXT 	  NOT NULL,
   created    TEXT 	  NOT NULL, -- lets not worry about parsing the timestamp
   edited     TEXT 	  NOT NULL  -- lets not worry about parsing the timestamp
);

-- insert into sql statement with qmark style placeholder - https://docs.python.org/3/library/sqlite3.html#sqlite3-placeholders
INSERT INTO swapi_people (id, name, height, mass, hair_color, skin_color, eye_color, birth_year, gender, created, edited)
VALUES(?, ?, ?, ?, ?, ?, ?, ?, ?, ?, ?);


-- insert into sql statement with named style placeholder - https://docs.python.org/3/library/sqlite3.html#sqlite3-placeholders
INSERT INTO swapi_people (id, name, height, mass, hair_color, skin_color, eye_color, birth_year, gender, created, edited)
VALUES(:id, :name, :height, :mass, :hair_color, :skin_color, :eye_color, :birth_year, :gender, :created, :edited);
  
```

### Python and sqlite3

```python
# this package is part of the core python modules
import sqlite3


# create a connection - database stored in a local file called "example.db"
conn = sqlite3.connect("example.db")


# execute SQL with context handler
with conn:
    conn.execute("select * from swapi_people;")


# execute INSERT SQL with context handler - https://docs.python.org/3/library/sqlite3.html#sqlite3.Cursor.execute
with conn:
    conn.execute(insert_sql_from_above, person)


# execute multiple INSERT SQL with context handler - https://docs.python.org/3/library/sqlite3.html#sqlite3.Cursor.executemany
with conn:
    conn.executemany(insert_sql_from_above, person_list)
```
