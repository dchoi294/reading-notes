# Class 12 Reading Note

In your own words, describe what each group of status code represents:

100’s = Wrong information from the client side  
200’s = Success codes  
300’s = requested is not available  
400’s = client error codes  
500’s = server error codes  

What is a status code 202?

- This code tells the client that the request was valid, but its processing will finish sometime in the future. The response body should include an URL to the finished resource with some information about when it will be available, or an URL to some monitoring endpoint that tells the client when the resource is available.

What is a status code 308?

- This tells the client to use another URL to access the resource and not use the current URL anymore. It’s helpful when we have multiple endpoints for one resource, but don’t want to implement reading from all of them.

What code would you use if an update didn’t return data to a client?

- 204 No Content

What code would you use if a resource used to exist but no longer does?

- 401 Gone

What is the ‘Forbidden’ status code?

- The client has authorized or doesn’t need to authorize itself, but still has no permissions to access the resource.

Reference [Status Codes Based On REST Methods](https://www.moesif.com/blog/technical/api-design/Which-HTTP-Status-Code-To-Use-For-Every-CRUD-App/)

Why do we need to pull our MongoDB database string out of our server and put it into our .env?

- 

What is middleware?

- Software that provides common services and capabilities to applications outside of what's offered by the operating system.

What does app.use(express.json()) do?

- It parses incoming requests with JSON payloads and is based on body-parser. Returns middleware that only parses JSON and only looks at requests where the Content-Type header matches the type option.

What does the /:id mean in a route?

- 

What is the difference between PUT and PATCH?

- PUT is a technique of altering resources when the client transmits data that revamps the whole resource. PATCH is a technique for transforming the resources when the client transmits partial data that will be updated without changing the whole data.

How do you make a default value in a schema?

- You can specify a default value for an item using the default keyword

What does a 500 error status code mean?

- The server encountered an unexpected condition that prevented it from fulfilling the request.

What is the difference between a status 200 and a status 201?

- It simply means that the request was received, understood, and is being processed, whereas the 201 status code indicates that a request was successful and a resource was created as a result

Reference [Build A REST API With Node.js, & MongoDB - Quick](https://www.youtube.com/channel/UCFbNIlppjAuEX4znoulh0Cw)

[Back to Home](../../README.md)  
