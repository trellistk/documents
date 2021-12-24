# Main HTTP Status Codes Used By Trellis ToolkitMeals

### 2xx Success
  * 200 - OK: The request has succeeded.
  * 201 - Created: The request has been fulfilled and resulted in a new resource being created.
  * 204 - No Content: The server fulfilled the request and doesn't need to return data, i.e a DELETE request.

### 4xx Client Error
  * 400 - Bad Request: The request cannot be fulfilled due to bad syntax. Basically your generalized client error when you can't use something more specific such as a 404.
  * 401 - Unauthorized: The request requires user authentication, and the user is either missing or has an invalid auth token.
  * 403 - Forbidden: User is forbidden from completing the request, regardless if they have proper authentication or not.
  * 404 - Not Found: Whatever the client requested isn't found on our server. Could also use instead of 401 or 403 for security-related reasons that you don't want the user to know about.

### 5xx Server Error
  * 500 - Internal Server Error: The general catch-all error when the server-side throws an exception.

### Useful Links For More Info
  * [REST API Tutorial's Helpful Page](https://www.restapitutorial.com/httpstatuscodes.html)
  * [RESTful API Design - Step By Step Guide](https://hackernoon.com/restful-api-design-step-by-step-guide-2f2c9f9fcdbf)