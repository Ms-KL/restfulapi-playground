# LinkedIn Learning - Learning REST API's

[LinkedIn](https://www.linkedin.com/learning/learning-rest-apis)

## Chapter 1: REST API: Representational State Transfer Application Programming Interface

### Chapter 1 Quiz:

- Question 1 of 6<br>
  A RESTful API is a service that runs on the web over HTTP to facilitate access to web resources. `TRUE`

- Question 2 of 6<br>
  Who can interact with a REST API? `Anyone, unless the REST API includes an authentication layer or similar access restrictions.`

- Question 3 of 6<br>
  What is the relationship between URIs, URLs, and URNs?
  `A URN can be a URL, and both are always URIs.`

- Question 4 of 6<br>
  REST is a stateless protocol. What does this mean?
  `No client context or information (aka “state”) can be stored on the server between requests.`

- Question 5 of 6<br>
  A representation of a resource is a unique copy of that resource, not the resource itself.
  `TRUE`

- Question 6 of 6<br>
  What is a REST API? `an application programming interface that follows the six constraints of REST`

## Chapter 2: Request:

### Chapter 2 Quiz:

- Question 1 of 4<br>
  What is a "resource"?`any information that can be named can be a resource`

- Question 2 of 4<br>
  The purpose of a REST method is to tell the REST server how to retrieve resources.`FALSE - The purpose of a REST method is to tell the REST server what to do with a resource.`

- Question 3 of 4<br>
  What is the minimum requirement to send a successful REST request?`The request must contain a method (verb) and a URI.`

- Question 4 of 4<br>
  What is the correct verb to discover what methods are available for a specific REST resource?`OPTIONS`

## Chapter 3: Response:

### Chapter 3 Quiz:

- Question 1 of 3<br>
  Who reads the response header? `Primarily the client application, but anyone can read it.`

- Question 2 of 3<br>
  A status message in the 400 range means: `The client made a mistake.`

- Question 3 of 3<br>
  An authorization header is used to change the authorization level of the currently logged in user.`FALSE - An authorization header is used to authenticate the user.`

## Chapter 4: Request/Response:

### Chapter 4 Quiz:

- Question 1 of 5<br>
  When you submit a DELETE request, what happens?`If the resource exists and you have the correct authorization, the resource is deleted or its status is changed on the server.`

- Question 2 of 5<br>
  What is the POST method used to do?`Post a new resource with a unique ID on the REST server.`

- Question 3 of 5<br>
  PUT/PATCH always do the same thing.`FALSE - PUT/PATCH are similar, but PUT replaces the entire resource, while PATCH only replaces the specified fields.`

- Question 4 of 5<br>
  Some requests get no response. This is a REST feature.`FALSE - All requests get a response, but some responses have no body.`

- Question 5 of 5<br>
  What is the GET method used to do?`Retrieve a resource from the REST server.`
