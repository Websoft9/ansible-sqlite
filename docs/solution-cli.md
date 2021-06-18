# CLI

SQLite provide `sqlite3` for user

## Manage command

```
# Create a database
sqlite3 testDB.db

# Get help
sqlite3 --help

# Check version
sqlite3 --version
```

## Interactive command

Run `sqlite3 testDB.db` command and go to SQLite interactive command status

```
# Get help
sqlite> .help

# Check database list
sqlite> .database

# Attach a database
sqlite> ATTACH DATABASE 'myDB.db' as 'TEST'

# Create table
sqlite> CREATE TABLE COMPANY(
   ID INT PRIMARY KEY     NOT NULL,
   NAME           TEXT    NOT NULL,
   AGE            INT     NOT NULL,
   ADDRESS        CHAR(50),
   SALARY         REAL
)

# Query table
sqlite> .tables
```