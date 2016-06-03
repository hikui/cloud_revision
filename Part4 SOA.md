# Service-oriented Architectures

## Why SOA

When components are distributed, function calls and object instantiations cannot always be used directly. Therefore, components have to interact in more loosely-coupled ways. *Services* are often used for this.

Every system in a SOA should be considered as _autonomous_, but network-reachable and inter-operable through services.

## Core ideas

* A ==set of services== that a business wants to provide to their customers, partners, or other areas of an organizaiton
* An architectural pattern that requires ==a service provider, mediaiton, and service requestor with a **service description**==
* A set of architectural principles, patterns and criteria that address ==characteristics== such as _modularity, encapsulation, loose coupling, seperation of concerns, reuse and composability_.
* A programming model complete with standards, tools and technologie that supports web services, REST services or other kinds of services.
* A middleware solution optimized for service assembly, orchestration, monitoring, and management.

## SOA Principles

* Standardized service contract: Services adhere to a ==communications agreement==, as defined collectively by one or more service-description documents
* Service loose coupling: Services maintain a relationship that minimizes dependencies and only requires that they ==maintain an awareness== of each other.
* Service abstraction: Beyond descriptions in the service contract, servies ==hide logic== from the outside world.
* Service reusability: Logic is ==divided== into services with the ==intention of promoting reuse==.
* Service autonomy: Service have control over the logic they encapsulate.
* Service statelessness: Service minimise resource consumption by deferring the management of state information when necessary (HTTP).
* Service discoverability: Service are supplemented with communicative meta data by which they can be effectively ==discovered and interpreted==.
* Service composability: Services are effective composition participants, regardless of the size and complexity of the composition.
* Service granularity(粒度): A design consideration to provide optimal scope at the right ==granular level== of the business functionality in a service operation.
* Service normalization: Services are decomposed and consolidated to alevel of normal form to ==minimize redundancy==. (In some cases they are denormalized for performance [same to database]).
* Service optimization: High quality services are generally preferable to low-quality ones.
* Service relevance: Functionality is presented at a granularity recognized by the user as a meaningful service.
* Service encapsulation: Many services are consolidated for use under a SOA. Often such services are not planned to be under a SOA.
* Service location transparency: The ability of a service consumer to invoke a service ==regardless of its actual location in the network.==

## SOAP/WS vs REST

Both use HTTP, hence can run over the web.

Two different architectural design:

* SOAP/WS is built on the paradigm of RPC; practically, a language independent function call that spans another system.
* REST is centered around resources, and the way they can be manipulated (HTTP actions) remotely.
* SOAP/WS is a stack of protocols that covers ==every aspect of using a remote service==, from service discovery to service description, to the actual request/response.

---

REST is very easy to understand and is extremely approachable, but does lack standards and is considered an architectural approach. In comparison, SOAP is an industry standard with a well-defined protocol and a set of well-established rules to be implemented, and it has been used in systems both big and small.

https://www.infoq.com/articles/rest-soap-when-to-use-each

## REST

![](img/REST.png)

1. Clients requests resource through URL.
2. Server sends representation of resource. (XML/JSON)
3. This puts the client in a certain ==state==.
4. Representation contains URLs ==allowing navigation==.
5. Client follows URL to fetch another resource.
6. Thes transitions client into another state.

### HATEOAS

HATEOAS stands for Hypertext As The Engine Of Application State. It means that _hypertext_(links) should be used to find your way through the API (navigate). 

* Resource representations contain links to identified resources.
* Resources and state can be used by navigating links.
* Navigate instead of calling:
	* Representations contain information about ==possible traversals==
	* The application navigates to the next resource depending on link semantics
	* navigation can be delegated since all links use identifiers ???

Example:

```xml
GET /account/12345 HTTP/1.1

HTTP/1.1 200 OK
<?xml version="1.0"?>
<account>
    <account_number>12345</account_number>
    <balance currency="usd">100.00</balance>
    <link rel="deposit" href="/account/12345/deposit" />
    <link rel="withdraw" href="/account/12345/withdraw" />
    <link rel="transfer" href="/account/12345/transfer" />
    <link rel="close" href="/account/12345/close" />
</account>

```

### Making resources navigable (RESTful)

RESTful systems use a Uniform Interface[^UniformInterface].

> The four constraints for this uniform interface are
>
> #### Identification of resources
> 
> Individual resources are identified in requests, for example using URIs in web-based REST systems. The resources themselves are conceptually separate from the representations that are returned to the client. For example, the server may send data from its database as HTML, XML or JSON, none of which are the server's internal representation.
>
> #### Manipulation of resources through these representations
> Each resource can have one or more representations. Such as `application/xml`, `application/json` etc. Clients and servers negotiate to select representation.
>
> #### Self-descriptive messages
> 
> Each message includes enough information to describe how to process the message. For example, which parser to invoke may be specified by an Internet media type (previously known as a MIME type).   
> MIME type example: `application/json` in the HTTP headers.
> 
> #### Hypermedia as the engine of application state (HATEOAS)
> 
> Clients make state transitions only through actions that are dynamically identified within hypermedia by the server (e.g., by hyperlinks within hypertext). Except for simple fixed entry points to the application, a client does not assume that any particular action is available for any particular resources beyond those described in representations previously received from the server.

#### How to find resources?

* Find them by following links from other resources.
* Learn about them by using URI Templates.
	* e.g. `api/{controller}/{id}`
* Understand them by recognizing representations.

### REST best practices
1. Keep your URIs short – and create URIs that don’t change. 
2. URIs should be opaque identifiers that are meant to be discovered by following hyperlinks, not constructed by the client.3. Use nouns, not verbs in URLs4. Make all HTTP GETs side-effect free. Doing so makes the request "safe".5. Use links in your responses to requests! Doing so connects your response with other data. It enables client applications to be "self-propelled". That is, ==the response itself contains info about "what's the next step to take"==. Contrast this to responses that do not contain links. Thus, the decision of "what's the next step to take" must be made out-of-band.
6. Minimize the use of query strings. For example: Prefer:   	http://www.amazon.com/products/AXFC   	Over:   	http://www.amazon.com/products?product-id=AXFC7. Use HTTP status codes to convey errors/success

### Resource-oriented architecture

Is a way of turning a problem into a RESTful web service: an arrangement of URIs, HTTP, and XML (or JSON) that works like the rest of the web.

#### When to make it a resource

If your users might:

* want to create a hypertext to it
* make or refute assertions about it ???
* retrieve or cache a reperesentation of it
* include all or part of it by reference into another representation
* annotate it
* perform other operations on it

#### An example of RESTful resource

![](img/RESTURL.png)

### HTTP methods

HTTP methods can be:

* Safe
* Idempotent
* Neigher

Safe methods: Don't change. Repeating a call is equivalent to not making a call at all. e.g. `GET`, `OPTIONS`, `HEAD`.

Idempotent methods: Effect of repeating a call is equivalent to making a single call. e.g. `PUT`, `DELETE`.

> More detailed explaination about idepotent methods:   
> Repeating means requesting the same URL with **the same method and data** repeatedly.  

### Mapping Actions to HTTP Methods

Action	|	HTTP Method
------	|	-----------
Create Resource	|	PUT with a new URI<br /> POST to a base URI returning a newly created URI
Retrieve Resource	|	GET
Update Resource	|	PUT to an existing URI
Delete Resource	| DELETE

#### When should we use PUT and when should we use POST?

The HTTP methods POST and PUT aren't the HTTP equivalent of the CRUD's create and update. They both serve a different purpose. It's quite possible, valid and even preferred in some occasions, to use PUT to create resources, or use POST to update resources.

Use PUT when you can update a resource completely through a specific resource. For instance, ==if you know that an article resides at http://example.org/article/1234, you can PUT a new resource representation of this article directly through a PUT on this URL==. (i.e. the ID of the article is generated by the client).

If you do not know the actual resource location, for instance, when you add a new article, but do not have any idea where to store it, you can POST it to an URL, and let the server decide the actual URL.

```xml
PUT /article/1234 HTTP/1.1
<article>
    <title>red stapler</title>
    <price currency="eur">12.50</price>
</article>
```

```xml
POST /articles HTTP/1.1
<article>
    <title>blue stapler</title>
    <price currency="eur">7.50</price>
</article>

HTTP/1.1 201 Created
Location: /articles/63636
```

You CAN add new resources through PUT as well. The next example is perfectly valid if your API provides this functionality:

```xml
PUT /articles/green-stapler HTTP/1.1
<article>
    <title>green stapler</title>
    <price currency="eur">9.95</price>
</article>

HTTP/1.1 201 Created
Location: /articles/green-stapler
```


[^UniformInterface]: https://en.wikipedia.org/wiki/Representational_state_transfer#Uniform_interface


