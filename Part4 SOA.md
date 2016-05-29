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
* Service loose copuling: Services maintain a relationship that minimizes dependencies and only requires that they ==maintain an awareness== of each other.
* Service abstraction: Beyond descriptions in the service contract, servies ==hide logic== from the outside world.
* Service reusability: Logic is ==divided== into services with the ==intention of promoting reuse==.
* 