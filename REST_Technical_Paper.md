## Understanding REST architecture and its constraints used in designing any modern day web architecture.
---
>## Abstract

Seventeen years, after it's initial publication at ICSE 2000, Representational State Transfer (REST) architecture continues to hold significance, as both a guide for understanding how the World Wide Web is designed to work, and an example of how principled
design, through the application of architectural styles, can impact the development and understanding of large-scale software architecture.
In this paper we will discuss about the constraints that help design any web architure. Also we will discuss about the main commands of REST architechture and thier uses.

---
>## Introduction
REST stands for REpresentational State Transfer and API stands for Application Program Interface. REST is a software architectural style that defines the set of rules to be used for creating web services. Web services which follow the REST architectural style are known as RESTful web services. It allows requesting systems to access and manipulate web resources by using a uniform and predefined set of rules. Interaction in REST based systems happen through Internet’s Hypertext Transfer Protocol (HTTP).

A Restful system consists of:

1. Client who requests for the resources.
2. Server who has the resources.

The client sends http request to the server for specific resources, and the server sends http response back to the client.

![REST Architecture](data:image/jpeg;base64,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)


### __What is a resource?__

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
>## Architectural Constraints of RESTful API
There are six architectural constraints, that are building blocks of any web service. These are listed below:

1. Uniform Interface
2. Stateless
3. Cacheable
4. Client-Server
5. Layered System
6. Code on Demand

The only optional constraint of REST architecture is code on demand. If a service violates any other constraint, it cannot strictly be referred to as RESTful.

### __1. Uniform Interface__
It is a key constraint that differentiate between a REST API and Non-REST API. It suggests that there should be an uniform way of interacting with a given server irrespective of the device or the type of application (website, mobile app).

There are four guidelines or principle of Uniform Interface. These are:

* __Resource-Based:__ Individual resources are identified in requests. For example: API/users. 
* __Manipulation of Resources Through Representation:__ Client has representation of resource and it contains enough information to modify or delete the resource on the server, provided it has permission to do so. Example: Usually user get a user id when user request for a list of users and then use that id to delete or modify that particular user.
* __Self-descriptive Messages:__ Each message includes enough information to describe how to process the message so that server can easily analyses the request.
* __Hypermedia as the Engine of Application State (HATEOAS):__ It need to include links for each response so that client can discover other resources easily.

### __2. Stateless__ 
It means that the necessary state to handle the request is contained within the request itself and server would not store anything related to the session. In REST, the client must include all information for the server to fulfill the request whether as a part of query parameters, headers or URI. Statelessness enables greater availability since the server does not have to maintain, update or communicate that session state. There is a drawback when the client need to send too much data to the server so it reduces the scope of network optimization and requires more bandwidth.

### __3. Cacheable__ 
Every response should include whether the response is cacheable or not and for how much duration responses can be cached at the client side. Client will return the data from its cache for any subsequent request and there would be no need to send the request again to the server. A well-managed caching, partially or completely, eliminates some client–server interactions, further improving availability and performance. But sometime there are chances that user may receive stale data.

### __4. Client-Server__
REST application should have a client-server architecture. A Client is someone who is requesting resources and are not concerned with data storage, which remains internal to each server, and server is someone who holds the resources and are not concerned with the user interface or user state. They can evolve independently. Client doesn’t need to know anything about business logic and server doesn’t need to know anything about frontend UI.

### __5. Layered system__ 
An application architecture needs to be composed of multiple layers. Each layer doesn’t know anything about any layer other than that of the immediate layer, and there can be lot of intermediate servers between client and the end server. Intermediary servers may improve system availability by enabling load-balancing and by providing shared caches.

### __6. Code on demand__ 
It is an optional feature. According to this, servers can also provide executable code to the client. The examples of code on demand may include the compiled components such as Java applets and client-side scripts such as JavaScript.

---
>## Rules of REST API
There are certain rules which should be kept in mind while creating REST API endpoints.
* REST is based on the resource or noun instead of action or verb based. It means that a URI of a REST API should always end with a noun. Example: /api/users is a good example, but /api?type=users is a bad example of creating a REST API.
* HTTP verbs are used to identify the action. Some of the HTTP verbs are – GET, PUT, POST, DELETE, UPDATE, PATCH.
* A web application should be organized into resources like users and then uses HTTP verbs like – GET, PUT, POST, DELETE to modify those resources. And as a developer it should be clear that what needs to be done just by looking at the endpoint and HTTP method used.
* Always use plurals in URL to keep an API URI consistent throughout the application.
* Send a proper HTTP code to indicate a success or error status.

### __HTTP verbs__
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
>## Conclusion
This paper talks about the REST architecture, and the design of web services using REST methodologies. The constraints which make a web service RESTful are discussed and the rules for a REST api are also discussed in this paper. 

REST is much easier than other approaches such as SOAP, which keeps developers from having to reinvent the wheel as far as HTTP request operations go. SOAP also requires separate server and client programs.

Since REST is based on standard HTTP operations, it uses verbs with specific meanings such as "get" or "delete" which avoids ambiguity. Resources are assigned to individual URIs, adding flexibility.

With REST, information that is produced and consumed is separated from the technologies that facilitate production and consumption. As a result, REST performs well, is highly scalable, simple, and easy to modify and extend.

>## Refrences
1. Tutorials and videos on youtube.
2. Geeksforgeeks https://www.geeksforgeeks.org/rest-api-architectural-constraints/
3. Restfulapi.net https://restfulapi.net/
4. Tutorailspoint https://www.tutorialspoint.com/restful/restful_quick_guide.htm