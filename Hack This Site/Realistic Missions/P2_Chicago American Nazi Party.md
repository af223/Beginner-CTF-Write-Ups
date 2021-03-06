# Chicago American Nazi Party

**goal:**
  - gain access to admin page and post on main page

**skill:** Structured Query Language (SQL)/SQL Injection

SQL is a language used to interact with databases. Its basic syntax is

`SELECT {field1} FROM {database} WHERE {field2}={value}`

This selects the 'field1' value in the database that matches with the given 'field2' value. 

SQL also uses logic operators like `AND`, `OR`, and `=`. `--` comments out everything that follows in that line.

SQL injections are a common attack that take advantage of when usernames and passwords are stored in a database, and the site doesn't clean user input of special characters. 
An example SQL statement might be
`SELECT * FROM users WHERE id="' + {userID input} + '" AND password="' + {password input} + '"`
. This returns all entries that matches the id and password field.

A basic SQL injection involves putting in 
`' OR '1=1'--`
for the password field.

Since 1=1 is always true, the OR statement is always true. Thus, without actually knowing the password, this would the database entry that matches the given ID.

---

Highlighting the whole page reveals a hidden link called update to a login page. Since you're looking for admin access, you can use 'admin' as the username. For the password, use an SQL injection
`' OR '1=1'--`
.
