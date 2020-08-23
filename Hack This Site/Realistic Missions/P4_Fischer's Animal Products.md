# Fischer's Animal Products

**goal:**
 - send the email address list of site's customers
 
 **skill:** SQL/SQL Injection
 
 Recall SQL from the Chicago American Nazi Party (mission 2).
 
 The UNION command allows you to get results from two SELECT statements. UNION ALL returns all results, including duplicates. The syntax for using UNION/UNION ALL statements:
 
 `SELECT id FROM table1 UNION ALL SELECT id2 FROM table2`
 
 You can figure out how many columns are in the table by using `UNION SELECT null--` and continuously adding 'null's until it doesn't return an error.
 `SELECT *` returns all entries.
 
Sources on the SQL UNION Operator and SQL Injection UNION attacks here:
[SQL UNION Operator](https://www.w3schools.com/sql/sql_union.asp)
[SQL Injection UNION attacks](https://portswigger.net/web-security/sql-injection/union-attacks)

---

Adding an improper email to the list returns error inserting into a table named "email" meaning no query is made from that field. Instead, looking at the other two links on the page, you'll see the HTML code is displaying data from another table. Using an SQL Injection, change the code for one of the links to

`href="products.php?category=2 UNION ALL SELECT null, null, *, null FROM email"`

This dumps all the emails on the list onto the linked page. Return back to hackthissite.org and send a message to SaveTheWhales with all the emails.
