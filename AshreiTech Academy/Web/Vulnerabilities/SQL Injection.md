It is a vulnerability where attacker manipulates queries interacting through the backend 
It held due to backend weakness as backend inject the user input directly in query

*Note: Test SQL injection perform where ever found input fields in the web*

SQL is a language to communicate with database 
DBMS is a software used for database (MS SQL, MYSQL, Postgres, Oracle)
	Each DBMS can have different payload injection

Two parts of the query:
- Data literal (strings,number)
- Query Logic (query)
### Types of SQL Injection
1) Union base SQL injection
2) Error base SQL injection
3) Blind base SQL injection
	- Time base SQL injection (Inject time base delay in query)
	- Boolean base SQL injection (Minor content alteration)

```
SELECT *
FROM users
WHERE username = 'test'
AND password = '123'
```

```
' OR '1' = '1' --
```

After SQL injection login bypass, it will login with the very first user return by database

SQL injection login Authentication bypass is due to backend code logic issue.

Report: User authentication bypass using SQL injection

Use -- or # for comment in SQL
### Union Base SQL Injection:
When results show on web page like product list page, we need to test the union base SQL injection
- Add `'` quote to inject
- Add `' OR 1 = 1`  and `' OR 1 = 2` Boolean injection

When found union base SQL injection, find number of columns exists in table
- Determine the number of columns of current query
```
UNION SELECT NULL --
```

```
 ' ORDER BY 20 --
```

- Determine the datatype of the column
```
' UNION SELECT NULL, 'a', NULL, NULL
```

*Note: Payload is always inject in the string data literal*

Finding Database Version
MS SQL/ MYSQL
```
' UNION SELECT NULL, @@version --
```

Oracle
```
' SELECT NULL, banner FROM v$version
```


### Error base SQL injection
It is a technique if SQL injection vulnerability exists or not.
It errors shows any info related to SQL query or version or response

### Blind base SQL injection

1) Time base SQL injection (Inject time base delay in query)
	It doesn't return all (DBMS version, table name, columns) at the same time. Need to find a character one by one
	
```
' OR IF(1=1, SLEEP(5), 0);
```
	
	substr or substring function that is used to test each character one by one
	
```
SUBSTR(string, start_position, length)

SUBSTR('a', 1, 12)
```

2) Boolean base SQL injection (Minor content alteration)
	 Minor response change when condition is true and false
	 
```
' OR 1 = 1
' OR 1 = 2
```

SQL Injection Metegation
### Parameterize query
A parameterized query is a secure way of writing SQL queries where user input is treated as data rather than executable SQL code.

```
username = request.form['username']

query = "SELECT * FROM users WHERE username = '" + username + "'"
```

### Input Validation
1) Black List
   Blacklist input validation is a security technique in which an application blocks specific characters, words, or patterns that are considered dangerous or unwanted.

2) White List
   Whitelist input validation is a security technique in which an application allows only predefined, acceptable characters, values, or formats.