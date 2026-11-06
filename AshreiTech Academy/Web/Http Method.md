
```
Get, Post, Put, Delete, Options
```

*Note*: Do not pass any sensitive information in the get method.
- Browser history can expose get method URL sensitive data
- Server also maintain history of requests
- Referer header also shows those get method query params
Report vuln: Sensitive data been passed in the get method

Vuln: try to use post method where get allowed, and get where post allowed
Report vuln: Wrong use of http method

When wrong http status code
Report vuln: Http response status code mismatch

In post method, file uploaded are stored as a new copy even with same name.
While in put it will override the existing files.
If found any directory listing, try to upload file there using put method.