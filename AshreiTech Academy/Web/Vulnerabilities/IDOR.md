## Insecure Direct Object Reference
IDOR happens when a user can access someone else's information just by changing an ID in a URL or request.

- URL query param in GET method (?userid=1)
- URL param in GET method (courses/5)
- POST method body passing any ID
- Cookie / Header (Always decode it)
- Indirect / Hashed / Encoded (Always decode or crack hash)
  
IDOR can happen on all HTTP methods (GET, POST, PUT, PATCH, DELETE)
