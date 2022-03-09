# Pair Programming Brief 


## Context

The business wants to extend selling of products beyond Earth and wants to target the wider galaxy. To better understand the target audience, the business has requested analysing the target customer profiles available from the Star Wars API.


## Ask

Create a new data ingestion pipeline/job: 

* ingest all “people” data from the Star Wars API - https://swapi.dev/documentation#people
    * the API provided unique id for each person should be preserved
    
* Data should land into the Data Warehouse:
    * SQLite - https://docs.python.org/3/library/sqlite3.html

* This would be an ongoing daily ingestion because:

   1. capture new people that are born in the Star Wars universe
   1. capture existing people who may have decided to change their hair colour, etc

* Your colleagues in the team have [already defined a database table schema](./gists.md#sql-statements) for you to use
    * creation/maintenance of this table should be handled by this ingestion pipeline/job


### Considerations for:

* testing
* robustness
* scalability
* deployment
