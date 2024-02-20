# DB-Setup
DBSetup: Streamline Your Database Setup with Docker-Compose. Simplify database configuration, including data importation, using Docker-Compose. Get up and running quickly with this efficient repository

## Pre-requisite
- Docker and Docker-compose must be installed.
- Docker service must be running.

## Setup
1. Create a `.env` file in the root directory.
2. Add `username` and `password` variables to the `.env` file.<br>
    `POSTGRES_USER=<username>`<br>
    `POSTGRES_PASSWORD=<password>`<br>

## Run
Run the following command. It will pull the PostgreSQL image and import data.
```bash
docker-compose up
```
following logs are observed in docker container

```bash
db-1  | server started
db-1  | CREATE DATABASE
db-1  |
db-1  |
db-1  | /usr/local/bin/docker-entrypoint.sh: running /docker-entrypoint-initdb.d/1_init.sql
db-1  | psql:/docker-entrypoint-initdb.d/1_init.sql:2: NOTICE:  table "question" does not exist, skipping
db-1  | DROP TABLE
db-1  | CREATE TABLE
db-1  | DROP TABLE
db-1  | psql:/docker-entrypoint-initdb.d/1_init.sql:15: NOTICE:  table "quiz" does not exist, skipping
db-1  | CREATE TABLE
db-1  | psql:/docker-entrypoint-initdb.d/1_init.sql:21: NOTICE:  table "quiz_questions" does not exist, skipping
db-1  | DROP TABLE
db-1  | CREATE TABLE
db-1  |
db-1  |
db-1  | /usr/local/bin/docker-entrypoint.sh: running /docker-entrypoint-initdb.d/2_questions_data.sql
db-1  | INSERT 0 26
```


## Verification
Once the database starts, connect to it using a database client like pgAdmin, DBeaver

From host connect on port 5442 with the `username` and `password` from the `.env` file.