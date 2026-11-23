Broken access control (Authorization bypass)
- Vertical access control (Higher access level)
- Horizontal access control (Same access level)
*Note: Required at least two account to check broken access control* 

- IDOR
- Check admin end points with normal user session cookie (Using burp extension authorize)
- Check end points without login session

#### Bypasses
- Sometimes 302 redirection on normal user cookie also reveal information

#### SQL MAP
```
sqlmap -r <file_path.txt> --batch
```

```
sqlmap -r <file_path.txt> --dbms=mysql --db --technique=T -D <database_name>
```

```
sqlmap -r <file_path.txt> --dbms=mysql --db --technique=T -D <database_name> -T <table_name>
```

- Can put * on the input field to only test that specific field 