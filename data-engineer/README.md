# Pair Programming Brief 


## Context

The business wants to extend selling of products beyond Earth and wants to target the wider galaxy. To better understand the target audience, the business has requested analysing the target customer profiles available from the Star Wars API.


## Ask

* ingest all “people” data from the Star Wars API - https://swapi.dev/documentation#people
    * the API provided unique id for each person should be preserved
    
* Data should land into the business Data Warehouse:
    * SQLite - https://docs.python.org/3/library/sqlite3.html

* Your colleagues in the team have already defined a schema for you to use, assume this table has not been created:

```sql
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
```

This would be an ongoing daily ingestion because:

1. capture new people that are born in the Star Wars universe
2. capture existing people who may have decided to change their hair colour

### Considerations for:

* testing
* robustness
* scalability
* deployment
