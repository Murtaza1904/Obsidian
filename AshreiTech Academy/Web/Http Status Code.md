## Status Code
The codes run that return in response of the client http requests that tells server response status.
100-199: Informational
200-299: Success
- 200: OK 
- 201: Created
- 204: Successful request, no response body
300-399: Redirection
- 301: Permanent redirection
- 302: Temporary redirection
- 304: `Not Modified` – Cached resource can be used
400-499: Client errors
- 400: Invalid payload or WAF protection blocking payload
- 401: Unauthorized
- 403: Forbidden
- 404: Resource not found
- 405: Method not allowed
- 429: Too many request
500-599: Server errors
- 500: Internal server error
- 503: Service unavailable