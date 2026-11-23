## Insecure Direct Object Reference
IDOR happens when a user can access someone else's information just by changing an ID (or Unique Identifier) in a URL or request. (Broken Access Control)

- URL query param in GET method (?id=1001)
- URL param in GET method (courses/5)
- POST method body passing any ID
- Cookie / Header (Always decode it)
- Indirect / Hashed / Encoded (Always decode or crack hash)
  
IDOR can happen on all HTTP methods (GET, POST, PUT, PATCH, DELETE)

Examples:
- Sequential Integer (?id=1001)
- Timestamp 
- Encoded
- MD5
- UUID (128 bit) (Format: 8-4-4-4-12)
- GUID (by Microsoft)

Solution:
- Use UUID/GUID
- Apply global authorization on the server side