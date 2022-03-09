## Understanding REST architecture and its constraints used in designing any modern day web architecture.
---
### Abstract

Seventeen years, after it's initial publication at ICSE 2000, Representational State Transfer (REST) architecture continues to hold significance, as both a guide for understanding how the World Wide Web is designed to work, and an example of how principled
design, through the application of architectural styles, can impact the development and understanding of large-scale software architecture.
In this paper we will discuss about the constraints that help design any web architure. Also we will discuss about the main commands of REST architechture and thier uses.

---
### Introduction
REST stands for REpresentational State Transfer and API stands for Application Program Interface. REST is a software architectural style that defines the set of rules to be used for creating web services. Web services which follow the REST architectural style are known as RESTful web services. It allows requesting systems to access and manipulate web resources by using a uniform and predefined set of rules. Interaction in REST based systems happen through Internet’s Hypertext Transfer Protocol (HTTP).

A Restful system consists of:

1. Client who requests for the resources.
2. Server who has the resources.

The client sends http request to the server for specific resources, and the server sends http response back to the client.

#### __What is a resource?__

The key abstraction of information in REST is a resource. Any information that we can name can be a resource. For example, a REST resource can be a document or image, a temporal service, a collection of other resources, or a non-virtual object (e.g., a person).

The state of the resource, at any particular time, is known as the resource representation. Once a resource is identified, then its representation is to be decided using a standard format so that the server can send the resource in the above said format and client can understand the same format.

The resource representation consist of:

1. The data.
2. The metadata describing the data.
3. The hypermedia links that can help the clients in transition to the next desired state.

REST does not impose any restriction on the format of a resource representation. A client can ask for JSON representation, whereas another client may ask for XML representation of the same resource to the server. It is the responsibility of the REST server to pass the resource, to the client, in the format that the client understands.

Following are some important points to be considered while designing a representation format of a resource in RESTful Web Services.

* __Understandability −__ Both the Server and the Client should be able to understand and utilize the representation format of the resource.

* __Completeness −__ Format should be able to represent a resource completely. For example, a resource can contain another resource. Format should be able to represent simple as well as complex structures of resources.

* __Linkablity −__ A resource can have a linkage to another resource, a format should be able to handle such situations.

However, at present most of the web services are representing resources using either XML or JSON format. There are plenty of libraries and tools available to understand, pass, and modify XML and JSON data.

---
### Architectural Constraints of RESTful API
There are six architectural constraints, that are building blocks of any web service. These are listed below:

1. Uniform Interface
2. Stateless
3. Cacheable
4. Client-Server
5. Layered System
6. Code on Demand

The only optional constraint of REST architecture is code on demand. If a service violates any other constraint, it cannot strictly be referred to as RESTful.

#### __1. Uniform Interface__
It is a key constraint that differentiate between a REST API and Non-REST API. It suggests that there should be an uniform way of interacting with a given server irrespective of the device or the type of application (website, mobile app).

There are four guidelines or principle of Uniform Interface. These are:

* __Resource-Based:__ Individual resources are identified in requests. For example: API/users. 
* __Manipulation of Resources Through Representation:__ Client has representation of resource and it contains enough information to modify or delete the resource on the server, provided it has permission to do so. Example: Usually user get a user id when user request for a list of users and then use that id to delete or modify that particular user.
* __Self-descriptive Messages:__ Each message includes enough information to describe how to process the message so that server can easily analyses the request.
* __Hypermedia as the Engine of Application State (HATEOAS):__ It need to include links for each response so that client can discover other resources easily.

#### __2. Stateless__ 
It means that the necessary state to handle the request is contained within the request itself and server would not store anything related to the session. In REST, the client must include all information for the server to fulfill the request whether as a part of query parameters, headers or URI. Statelessness enables greater availability since the server does not have to maintain, update or communicate that session state. There is a drawback when the client need to send too much data to the server so it reduces the scope of network optimization and requires more bandwidth.

#### __3. Cacheable__ 
Every response should include whether the response is cacheable or not and for how much duration responses can be cached at the client side. Client will return the data from its cache for any subsequent request and there would be no need to send the request again to the server. A well-managed caching, partially or completely, eliminates some client–server interactions, further improving availability and performance. But sometime there are chances that user may receive stale data.

#### __4. Client-Server__
REST application should have a client-server architecture. A Client is someone who is requesting resources and are not concerned with data storage, which remains internal to each server, and server is someone who holds the resources and are not concerned with the user interface or user state. They can evolve independently. Client doesn’t need to know anything about business logic and server doesn’t need to know anything about frontend UI.

#### __5. Layered system__ 
An application architecture needs to be composed of multiple layers. Each layer doesn’t know anything about any layer other than that of the immediate layer, and there can be lot of intermediate servers between client and the end server. Intermediary servers may improve system availability by enabling load-balancing and by providing shared caches.

#### __6. Code on demand__ 
It is an optional feature. According to this, servers can also provide executable code to the client. The examples of code on demand may include the compiled components such as Java applets and client-side scripts such as JavaScript.

---
### Rules of REST API
There are certain rules which should be kept in mind while creating REST API endpoints.
* REST is based on the resource or noun instead of action or verb based. It means that a URI of a REST API should always end with a noun. Example: /api/users is a good example, but /api?type=users is a bad example of creating a REST API.
* HTTP verbs are used to identify the action. Some of the HTTP verbs are – GET, PUT, POST, DELETE, UPDATE, PATCH.
* A web application should be organized into resources like users and then uses HTTP verbs like – GET, PUT, POST, DELETE to modify those resources. And as a developer it should be clear that what needs to be done just by looking at the endpoint and HTTP method used.
* Always use plurals in URL to keep an API URI consistent throughout the application.
* Send a proper HTTP code to indicate a success or error status.

#### __HTTP verbs__
Some of the common HTTP methods/verbs are described below:

* __GET:__ Retrieves one or more resources identified by the request URI and it can cache the information receive.

* __POST:__ Create a resource from the submission of a request and response is not cacheable in this case. This method is unsafe if no security is applied to the endpoint as it would allow anyone to create a random resource by submission.

* __PUT:__ Update an existing resource on the server specified by the request URI.

* __DELETE:__ Delete an existing resource on the server specified by the request URI. It always return an appropriate HTTP status for every request.

Some examples are listed below:

URI	HTTP        |verb	  |    Description
----------------|---------|-----------------------------
api/users	    |GET	  |Get all users
api/users/new	|GET	  |Show form for adding new user
api/users	    |POST	  |Add a user
api/users/1	    |PUT	  |Update a user with id = 1
api/users/1/edit|GET	  |Show edit form for user with id = 1
api/users/1	    |DELETE	  |Delete a user with id = 1
api/users/1	    |GET	  |Get a user with id = 1

----
### Conclusion
This paper talks about the REST architecture, and the design of web services using REST methodologies. The constraints which make a web service RESTful are discussed and the rules for a REST api are also discussed in this paper. 

REST is much easier than other approaches such as SOAP, which keeps developers from having to reinvent the wheel as far as HTTP request operations go. SOAP also requires separate server and client programs.

Since REST is based on standard HTTP operations, it uses verbs with specific meanings such as "get" or "delete" which avoids ambiguity. Resources are assigned to individual URIs, adding flexibility.

With REST, information that is produced and consumed is separated from the technologies that facilitate production and consumption. As a result, REST performs well, is highly scalable, simple, and easy to modify and extend.

---

### Refrences
1. Tutorials and videos on youtube.
2. Geeksforgeeks https://www.geeksforgeeks.org/rest-api-architectural-constraints/
3. Restfulapi.net https://restfulapi.net/
4. Tutorailspoint https://www.tutorialspoint.com/restful/restful_quick_guide.htm
