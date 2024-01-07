

Node.js

Bun

written in Zig

Applications that can be created outside the browser environment

- CLIs
- Create a video player
- Create a game
- Create an HTTP Server (90% use case)

What is HTTP Server

- HTTP - Hyper Text Transfer Protocol
- HTTP is a protocol that is defined for machines to communicate
- Mostly for frontend to backend
- HTTP Server - Code that follows HTTP Server. It could be any code that takes input through a request using HTTP protocol and sends the response through HTTP protocol.

What is needed by the client to make a HTTP request ?

- Address (URL/ IP/ Port) and path => URL structure: protocol(http/https)://url(domain/ip address)/route(path)?query_parameters
- Method (Common methods: GET, HEAD, POST, PUT, PATCH, DELETE)
- Header - Cookies
- Request Body - (content - usually JSON, can contain File etc)

You can view this by dev tools - network tab.

What is needed by the Server ?

- Response header (mostly used in sign in request to send cookie)
- Response body 
- Status codes

Why request/ response are structured this way ?

- It is based on Specification similar to language standards, these are based on protocol standards.

What happens when you hit a a URL in browser ?

- Answer this at a high level

Express

- Express is a node js web application framework that provides broad features for building web and mobile applications.

Why do you need port ?



