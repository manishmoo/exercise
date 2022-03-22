# Pair Programming Brief 


## Context

The business wants to extend selling of products beyond Earth and wants to target the wider galaxy. To better understand the target audience, the business wants to start looking into intergalactic customer profiles available from the Star Wars API.


## Ask

Create a new daily data ingestion pipeline/job in `Python 3.10` to keep upto date with all the people in the Star Wars universe: 

1. Ingest all `people` data from the Star Wars API - https://swapi.dev/
    * the API provided unique "people id" for each person should be captured
    
1. The `people` data should land into the Data Warehouse:
    * SQLite - https://docs.python.org/3/library/sqlite3.html

1. Your colleagues in the team have [already defined a database table schema](./gists.md#sql-statements) for you to use
    * creation/maintenance of this table should be handled by this ingestion pipeline/job

1. Capture any changes to existing people in the universe
    * E.g. if C3PO decides to go blonde, the existing record in the Warehouse should reflect this



### Considerations for:

* testing (please include at least 1 test)
* robustness
* scalability
* readability
* deployment
