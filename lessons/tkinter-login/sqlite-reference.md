# SQLite Reference

## Setting Up

`sqlite3` is a built-in module for Python so no install is required. Just import it at the top of your code:

```python
import sqlite3
```

You could also use this code as a template:

```python
import sqlite3                # Import SQLite

conn = sqlite3.connect("myDatabase.db") # Create a new database if one doesn't exist
                                        # or if one does, open it.
c = conn.cursor()             # Make a new cursor which is used to interface with the
                              # database.

### WRITE ANY CODE HERE ###

conn.commit()                 # Save changes to the database file. Should be used
                              # before the program quits. Ideally it should be
                              # ran regularly.
conn.close()                  # Close the connection to the database file. Should
                              # be used before the program quits.
```

## Executing Commands

```python
c.execute("SELECT * FROM mydatabase") # Execute an SQL Query on the database.

idToSearchFor = 15
c.execute("SELECT * FROM mydatabase WHERE id=?", idToSearchFor) # Execute an SQL
                                                                # Query with an
                                                                # input.

output = c.fetchall()         # Get the results from the executed Query.
```

## Creating Tables

```sql
CREATE TABLE myTable (id number, name text, email text)
```

Where `id`, `name` or `email` is the name of the column.

Where `number`, `text` or `email` is the data type which can be `text`, `number` and `real` *(there are more but these are the most common)*.

## Inserting Data

```sql
INSERT INTO myTable (id, name, email) VALUES (1337, "Jeff", "jeff@gmail.com")
```

```python
id = 1337
name = "Jeff"
email = "jeff@gmail.com"

c.execute("INSERT INTO myTable (id, name, email) VALUES (?, ?, ?)", [id, name, email])
```

## Deleting Data

```sql
DELETE FROM myTable WHERE name = "Jeff"
```

```python
name = "Jeff"

c.execute("DELETE FROM myTable WHERE name = ?", [name])
```

## Retriving Data

```sql
SELECT * FROM myTable
/* Returns all rows in the table */
```

```sql
SELECT name FROM myTable
/* Returns all names in table */
```

```sql
SELECT * FROM myTable WHERE name="Fred"
/* Returns row for Fred */
```

```python
name = "Fred"

c.execute("SELECT * FROM myTable WHERE name=?", [name])
print(c.fetchall());
```
