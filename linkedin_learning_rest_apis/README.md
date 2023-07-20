# LinkedIn Learning REST APIs<br> Course Notes

## Resources:

- [LinkedIn Learning: Learning REST API's](https://www.linkedin.com/learning/learning-rest-apis/)
- [Public Hosted REST using AJAX requests](https://reqres.in/)
- see [rest requests](/restrequests.http) for examples

## About REST API:

### Client - API - Database - API - Client flow:

1. Client sends a request to the API. The following is required for the request:

   - **HTTP Method**
     - eg: GET, POST, PUT, DELETE
   - **URI**
     - eg: https://www.example.com/index.html
   - **HTTP Version**
     - eg: HTTP/1.1
   - **Request Header**
     - eg: Content-Type: application/json
   - **Request Body**
     - eg: { "name": "Kristy" }

2. API receives the request and accesses the database

   - database examples: MySQL, MongoDB, PostgreSQL, Oracle, SQL Server
   - eg: SELECT \* FROM users WHERE name = "Kristy" (this is a SQL query)

3. API sends a response from the database to the client.The following is required for the response:
   - HTTP Version
   - Status Code
   - Status Message
   - Response Header
   - Response Body

### 6 Constraints of REST:

Send request through HTTP protocol

1. Client-Server Architecture
   - this means that the client and the server are separated from each other
2. Stateless
   - this means that the server does not store any state about the client session on the server side
3. Cacheable
   - this means that the server must indicate whether the client can cache the response. Cache is a temporary storage
4. Layered System
   - this means that the client cannot tell whether it is connected to the end server or to an intermediary along the way
5. Uniform Interface
   - this means that the client and the server must be able to communicate with each other in a uniform way
6. Code on Demand
   - this means that the server can extend the functionality of the client by transferring executable code

### HTTP Methods:

- GET: Retrieve data from a specified resource
- POST: Submit data to be processed to a specified resource
- PUT: Update a specified resource
- DELETE: Delete a specified resource
- HEAD: Same as GET but does not return a body
- OPTIONS: Returns the supported HTTP methods
- PATCH: Update partial resources

### HTTP Status Codes:

- 1xx: Informational
- 2xx: Success
- 3xx: Redirection
- 4xx: Client Error
- 5xx: Server Error

### HTTP Headers:

- General Headers: Apply to both request and response messages
- Request Headers: Contains more information about the resource to be fetched or about the client requesting the resource
- Response Headers: Contains more information about the response
- Entity Headers: Contains more information about the body of the entity, like its content length or MIME type

### HTTP Request:

- Request Line: Contains the HTTP method, the URI, and the HTTP version
- Request Header: Contains more information about the request
- Blank Line: Separates the header and the body
- Request Body: Contains the data to be sent to the server

### HTTP Response:

- Status Line: Contains the HTTP version, the status code, and the status message
- Response Header: Contains more information about the response
- Blank Line: Separates the header and the body
- Response Body: Contains the requested resource

### URI, URL, URN

- URI: Uniform Resource Identifier. This is the generic term for all types of names and addresses that refer to objects on the World Wide Web

- URL: Uniform Resource Locator. this is a subset of the URI that identifies the resource by giving its location (eg: kristy's location = earth)

- URN: Uniform Resource Name. this is a subset of the URI that identifies the resource by name in a given namespace (eg: name = kristy)

- URI: http://www.example.com/index.html#posts
- URL: http://www.example.com/index.html (http)
- URN: example.com/index.html#posts
- Resource: #posts
- Location: .html

## Tools to see REST API in action:

### Reqres

- [Reqres](https://reqres.in/)

1. Browser: https://reqres.in/api/users?page=2
   ![list users](/assets/list_users.png)
   ![list users response](/assets/list_users_response.png) \* not parsed properly, hard to read --> need client for this purpose (postman, insomnia, etc)
2. DevTools
3. Network

### JSONPlaceholder

- [JSONPlaceholder](https://jsonplaceholder.typicode.com/)

## REST client tools:

- [REST Client for VS Code](https://vscode.dev/Huachao/vscode-restclient?from=open)
- [Postman](https://www.postman.com/)
- [Insomnia](https://insomnia.rest/)
- [cURL](https://curl.haxx.se/)
- [HTTPie](https://httpie.org/)
- [Paw](https://paw.cloud/)
- [Advanced REST Client](https://install.advancedrestclient.com/install)

## Anatomy of a REST Request:

- 2 parts: Method and URI

  - eg: `GET https://www.example.com/index.html`
    - Method: `GET, POST, PUT, DELETE, PATCH, HEAD, OPTIONS`
    - URI: Uniform Resource Identifier eg: `https://www.example.com/posts/5`
      - URL: Uniform Resource Locator eg: `https://www.example.com/posts/5`
      - URN: Uniform Resource Name eg: `example.com/posts/5`
      - Resource: `posts/5`
      - Location: `.html`

- GET request:
  ![get request](/assets/get_request.png)

  - using JavaScript:
    ![get request js](/assets/get_request_js.png)

- POST request: \* send data too (content-type must match data being sent)
  ![post request](/assets/post_request.png)
  - using JQuery Ajax:
    ![post request jquery ajax](/assets/post_request_jquery_ajax.png)

## Discovery:

- GET and OPTIONS show methods available for a resource:
  - see [rest requests](/restrequests.http) for examples

## Resources vs Representation:

- any information that can be named can be a resource (eg: a document, a photo, a video, a user, etc)
- RESOURCE: the data contained at the end of the resource URI (actual entity)
- REPRESENTATION: representation of the data obtained (copy of the entity)
  - resource is a CONCEPTUAL MAPPING to a set of entities --> NOT the entity itself
  - resource is a NOUN
  - eg: librarian:
    - Verb: GET
    - Resource: Bookcase:shelf:4:red <-- conceptual mapping to a set of books
      - resource collection: "all red books" (eg: bookcase/books/red)
      - resource singleton: "red book in shelf 4" (eg: bookcase/books/red/4)
  - representation:
    - REST server generates a unique copy of that entity to fit requirements of the client
    - a resource can have multiple representations (it wont return the actual entity, it will return a representation of the entity)
    - eg: bookcase/books/red/4
      - representation: JSON
      - representation: XML
      - representation: HTML
      - representation: PDF
      - representation: CSV
      - representation: etc

## Methods:

- GET: retrieve data from a specified resource
  - successful GET returns 200 OK
  - unsuccessful GET returns 404 Not Found
- POST: submit data to be processed to a specified resource
  - successful POST returns 201 Created (+link to new resource ID in header)
  - unsuccessful POST returns 400 Bad Request, 401 Unauthorized, 403 Forbidden, 404 Not Found, 405 Method Not Allowed, 409 Conflict (Already exists)
- PUT: update a specified resource based on ID
  - successful PUT returns 200 OK (content replaced)
  - unsuccessful PUT returns 400 Bad Request, 401 Unauthorized, 403 Forbidden, 404 Not Found, 405 Method Not Allowed, 409 Conflict (Already exists)
- DELETE: delete a specified resource
  - successful DELETE returns 200 OK (content deleted)
  - unsuccessful DELETE returns 401 Unauthorized, 404 Not Found, 405 Method Not Allowed (delete all), 409 Conflict (Already exists)
- HEAD: same as GET but does not return a body
- OPTIONS: returns the supported HTTP methods
  - successful OPTIONS returns 200 OK (content deleted)
  - unsuccessful OPTIONS returns 401 Unauthorized, 404 Not Found, 405 Method Not Allowed, 409 Conflict (Already exists)
- PATCH: update partial resources
  - successful PATCH returns 200 OK (content updated)
  - unsuccessful PATCH returns 400 Bad Request, 401 Unauthorized, 403 Forbidden, 404 Not Found, 405 Method Not Allowed, 409 Conflict (Already exists)

## Response:

- every response from REST API will have a head section
- See [rest responses](/restresponses.http) for examples
- head section contains:
  - HTTP version
  - status code
    - 1xx: Informational
      - informs the client that the server has received the request and is continuing to process it
    - 2xx: Success
      - indicates that the request was successfully received, understood, and accepted
    - 3xx: Redirection
      - indicates that the client must take some additional action in order to complete their request
    - 4xx: Client Error
      - indicates that the client has sent a bad request (eg: wrong URI, wrong HTTP method, etc)
    - 5xx: Server Error
      - indicates that the server failed to fulfill an apparently valid request (internal server error, bad gateway, service unavailable, etc)
  - status message
  - response header (line 1)
