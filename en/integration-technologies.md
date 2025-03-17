---
title: "Integration technologies"
description: "Integration technologies in sofware development"
keywords: "ESB, EMS, RPC, GraphQL, gRPC, JSON, XML, XPath"
lang: "en"
permalink: "integration-technologies"
aliases:
  - "integration-technologies"
---

# Integration technologies

## Overview

**Main reference:** [https://www.enterpriseintegrationpatterns.com/](https://www.enterpriseintegrationpatterns.com/) This pattern catalog describes 65 integration patterns, collected from many integration projects since 2002. The patterns provide technology-independent design guidance for developers and architects to describe and develop robust integration solutions. The inspiration to document these patterns came when we struggled through multiple integration vendors' product documentation just to realize later that many of the underlying concepts were quite similar.

Three approaches to information systems integration

* Integration at the data level. The essence of this approach is as follows: applications work independently of each other, each using its own set of data. If necessary, data is exchanged between applications. At the same time, if data exchange is carried out by calling services or sending/receiving messages, then the Enterprise Service Bus (ESB) can be used as a medium for exchange. If data exchange is carried out mainly between databases used by a particular application, then you can use the Extract, Transform, Load (ETL) class solution.
* Integration at the level of business processes. The essence of this approach is as follows: applications expose services that are interfaces to the business logic of these applications. Interaction between applications is implemented within the framework of a business process, at individual steps of which a particular service is called. This approach is implemented using the enterprise service bus (ESB), which is engaged in the virtualization of services provided by applications, and Business Process Management System (BPMS) class solutions, usually based on the BPEL or BPMN languages that implement the process logic.
* Integration at the level of composite applications. The business logic of an individual application is built by calling services provided both by this application and by other systems. Thus, several services can interact at one step of a business process, while with integration at the business process level, one service is called at one step of the process.

## ESB

[https://en.wikipedia.org/wiki/Enterprise\_service\_bus](https://en.wikipedia.org/wiki/Enterprise_service_bus)

An enterprise service bus (ESB) implements a communication system between mutually interacting software applications in a service-oriented architecture (SOA). It represents a software architecture for distributed computing, and is a special variant of the more general client-server model, wherein any application may behave as server or client. ESB promotes agility and flexibility with regard to high-level protocol communication between applications. Its primary use is in enterprise application integration (EAI) of heterogeneous and complex service landscapes.

The concept of the enterprise service bus is analogous to the bus concept found in computer hardware architecture combined with the modular and concurrent design of high-performance computer operating systems. The motivation for the development of the architecture was to find a standard, structured, and general purpose concept for describing implementation of loosely coupled software components (called services) that are expected to be independently deployed, running, heterogeneous, and disparate within a network. ESB is also a common implementation pattern for service-oriented architecture, including the intrinsically adopted network design of the World Wide Web.

No global standards exist for enterprise service bus concepts or implementations. Most providers of message-oriented middleware have adopted the enterprise service bus concept as de facto standard for a service-oriented architecture. The implementations of ESB use event-driven and standards-based message-oriented middleware in combination with message queues as technology frameworks. However, some software manufacturers relabel existing middleware and communication solutions as ESB without adopting the crucial aspect of a bus concept.

Notable products include:

* Proprietary
  * [Candle's Roma ESB - bought by IBM and became WebSphere ESB](https://en.wikipedia.org/w/index.php?title=Candle%27s_Roma_ESB_-_bought_by_IBM_and_became_WebSphere_ESB&action=edit&redlink=1 "Candle's Roma ESB - bought by IBM and became WebSphere ESB (page does not exist)")
  * [IBM](https://en.wikipedia.org/wiki/IBM "IBM") App Connect, formerly IBM Integration Bus and IBM WebSphere ESB
  * [InterSystems](https://en.wikipedia.org/wiki/InterSystems "InterSystems") Ensemble
  * [Information Builders](https://en.wikipedia.org/wiki/Information_Builders "Information Builders") iWay Service Manager
  * [Microsoft Azure](https://en.wikipedia.org/wiki/Microsoft_Azure "Microsoft Azure") Service Bus
  * [Microsoft BizTalk Server](https://en.wikipedia.org/wiki/Microsoft_BizTalk_Server "Microsoft BizTalk Server")
  * [Mule](<https://en.wikipedia.org/wiki/Mule_(software)> "Mule (software)") ESB
  * [Oracle Enterprise Service Bus](https://en.wikipedia.org/wiki/Oracle_Enterprise_Service_Bus "Oracle Enterprise Service Bus")
  * [Progress Software](https://en.wikipedia.org/wiki/Progress_Software "Progress Software") Sonic ESB (acquired by [Trilogy](<https://en.wikipedia.org/wiki/Trilogy_(company)> "Trilogy (company)"))
  * [SAP Process Integration](https://en.wikipedia.org/wiki/SAP_Process_Integration "SAP Process Integration")
  * [TIBCO Software](https://en.wikipedia.org/wiki/TIBCO_Software "TIBCO Software") ActiveMatrix BusinessWorks
  * [webMethods](https://en.wikipedia.org/wiki/WebMethods "WebMethods") enterprise service bus (acquired by [Software AG](https://en.wikipedia.org/wiki/Software_AG "Software AG"))
  * [Sonic ESB](https://en.wikipedia.org/wiki/Sonic_ESB "Sonic ESB") from Aurea
  * [XIATech](https://en.wikipedia.org/w/index.php?title=XIATech&action=edit&redlink=1 "XIATech (page does not exist)") Single Data View
* Open-source software
  * [Apache Camel](https://en.wikipedia.org/wiki/Apache_Camel "Apache Camel")
  * Apache ServiceMix
  * [Apache Synapse](https://en.wikipedia.org/wiki/Apache_Synapse "Apache Synapse")
  * [Fuse ESB](https://en.wikipedia.org/wiki/Fuse_ESB "Fuse ESB") from [Red Hat](https://en.wikipedia.org/wiki/Red_Hat "Red Hat")
  * [JBoss ESB](<https://en.wikipedia.org/wiki/JBoss_Enterprise_SOA_Platform#Enterprise_Service_Bus_(ESB)> "JBoss Enterprise SOA Platform")
  * [NetKernel](https://en.wikipedia.org/wiki/NetKernel "NetKernel")
  * [Open ESB](https://en.wikipedia.org/wiki/Open_ESB "Open ESB")
  * [Petals ESB](https://en.wikipedia.org/wiki/Petals_ESB "Petals ESB")
  * [Spring Integration](https://en.wikipedia.org/wiki/Spring_Integration "Spring Integration")
  * [UltraESB](https://en.wikipedia.org/wiki/UltraESB "UltraESB")
  * [WSO2 ESB](https://en.wikipedia.org/wiki/WSO2_ESB "WSO2 ESB")
  * [Zato](https://zato.io/) (in Python)

### EMS

[https://en.wikipedia.org/wiki/Enterprise\_messaging\_system](https://en.wikipedia.org/wiki/Enterprise_messaging_system)

An enterprise messaging system (EMS) or messaging system in brief\[1\] is a set of published enterprise-wide standards that allows organizations to send semantically precise messages between computer systems. EMS systems promote loosely coupled architectures that allow changes in the formats of messages to have minimum impact on message subscribers. EMS systems are facilitated by the use of structured messages (such as using XML or JSON), and appropriate protocols, such as DDS, MSMQ, AMQP or SOAP with web services.

## Integration protocols (popular)

### REST

REpresentational State Transfer REST, or REpresentational State Transfer, is an architectural style for providing standards between computer systems on the web, making it easier for systems to communicate with each other. REST-compliant systems, often called RESTful systems, are characterized by how they are stateless and separate the concerns of client and server. We will go into what these terms mean and why they are beneficial characteristics for services on the Web. Pay close attention: If you're looking for a career in tech, you may be asked to define rest during an interview. [https://www.codecademy.com/article/what-is-rest](https://www.codecademy.com/article/what-is-rest)

According to REST, a network resource must support only four operations: GET, PUT, POST and DELETE (with the same meanings as in the HTTP protocol). Data should be transmitted in a small number of standard formats (eg HTML, XML, JSON). The network protocol (like HTTP) must support caching, must not depend on the network layer, and must not store state information between request-response pairs. It is argued that this approach ensures scalability of the system and allows it to evolve with new requirements.

HTTP Verbs{#heading-http-verbs}

There are 4 basic HTTP verbs we use in requests to interact with resources in a REST system:

* GET - retrieve a specific resource (by id) or a collection of resources
* POST - create a new resource
* PUT - update a specific resource (by id)
* DELETE - remove a specific resource by id

#### REST URL pattern best practice

| Action |  HTTP  | Payload |         URL          |                    Description                    |
|--------|--------|---------|----------------------|---------------------------------------------------|
| Create | POST   | json    | /\<resource\>        | Create an entity represented by the JSON payload. |
| Read   | GET    | -       | /\<resource\>        | Get all entities from the resource.               |
| Read   | GET    | -       | /\<resource\>/\<id\> | Get a single entity.                              |
| Update | PUT    | json    | /\<resource\>/\<id\> | Update an entitiy with the JSON payload.          |
| Delete | DELETE | -       | /\<resource\>/\<id\> | Delete an entity.                                 |

Example

* All contacts: /contacts
* Individual contact: /contacts/{cID}
* Notes for contact: /contacts/{cID}/notes
* Individual note: /contacts/{cID}/notes/{nID}
* Emails for contact: /contacts/{cID}/emails
* Individual email: /email/{eID}

[https://blog.stoplight.io/crud-api-design](https://blog.stoplight.io/crud-api-design)

The nouns in URLs are the same that describe your domain model. When modeling your domain, pay attention to the following:

* Do not make nouns unnecessarily long and complicated (users, not system-users).
* Use common terminology (people instead of special-snowflakes).

Apart from the noun rules, there are a few other best practices that the industry has established and many companies have put down in their API style guides:

* Use lowercase (/items not /Items) to avoid the ambiguity around URL case-sensitivity.
* For individual resources, include resource identifiers in the path, not the query (/contacts/22 instead of /contacts?id=22).
* Paths that end with a resource name (and typically no trailing slash) are used to list multiple items (/files) or create items without specifying an identifier.
* Paths can indicate a hierarchy of subresources (/contacts/22/addresses), but API designers should avoid complex structures that require more than two levels of nesting.
* Nouns should be in the plural form (/files instead of /file) unless they describe a singleton.
* Nouns that are compounds of multiple words should use a hyphen as a separator (/legal-documents). There's a very mundane reason for this: when URLs are hyperlinks, they are often underlined, which would render an underscore separator invisible.
* URLs should never reveal the underlying implementation (/resources not /api.php/resources).
* The query part of the URL is for search and filtering and commonly used with a resource list endpoint (/contacts?first\_name=Anna\&limit=20).

[https://opensource.zalando.com/restful-api-guidelines/index.html#introduction](https://opensource.zalando.com/restful-api-guidelines/index.html#introduction)  
If you provide query support for searching, sorting, filtering, and paginating, you must stick to the following naming conventions:

* {#q}q: default query parameter, e.g. used by browser tab completion; should have an entity specific alias, e.g. sku.

* {#sort}sort: comma-separated list of fields (as defined by MUST define collection format of header and query parameters) to define the sort order. To indicate sorting direction, fields may be prefixed with + (ascending) or - (descending), e.g. /sales-orders?sort=+id.

* {#fields}fields: field name expression to retrieve only a subset of fields of a resource.

* {#embed}embed: field name expression to expand or embedded sub-entities, e.g. inside of an article entity, expand silhouette code into the silhouette object. Implementing embed correctly is difficult, so do it with care.

* {#offset}offset: numeric offset of the first element provided on a page representing a collection request.

* {#cursor}cursor: an opaque pointer to a page, never to be inspected or constructed by clients. It usually (encrypted) encodes the page position, i.e. the identifier of the first or last page element, the pagination direction, and the applied query filters to recreate the collection. See

* {#limit}limit: client suggested limit to restrict the number of entries on a page.

### RPC

The antipode of REST is an approach based on remote procedure calls (RPC). The RPC approach allows the use of a small number of network resources with a large number of methods and a complex protocol. With the REST approach, the number of methods and the complexity of the protocol are strictly limited, which is why the number of individual resources must be large

### GraphQL

[https://en.wikipedia.org/wiki/GraphQL](https://en.wikipedia.org/wiki/GraphQL)

[https://graphql.org/](https://graphql.org/)

GraphQL is an open-source data query and manipulation language for APIs and a query runtime engine. GraphQL enables declarative data fetching where a client can specify exactly what data it needs from an API. Instead of multiple endpoints that return separate data, a GraphQL server exposes a single endpoint and responds with precisely the data a client asked for. Because a GraphQL server can fetch from separate data sources and present the data in a unified graph, it is not tied to any specific database or storage engine. acebook started GraphQL development in 2012 and released it as open source in 2015.In 2018, GraphQL was moved to the newly established GraphQL Foundation, hosted by the non-profit Linux Foundation.

GraphQL же позволяет передать в приложение сразу нужные данные за один запрос, даже если они находятся в нескольких источниках. Благодаря этому технология извлечения данных GraphQL удобнее и практичнее, чем REST.

GraphQL Features:

* There is no need to create multiple REST requests. To extract data, just enter one query.
* Not tied to a specific database or storage mechanism.
* A whole system of data types is used.

The GraphQL API is built on two main blocks: queries and schema.

### OData

[https://www.odata.org/](https://www.odata.org/)

[https://en.wikipedia.org/wiki/Open\_Data\_Protocol](https://en.wikipedia.org/wiki/Open_Data_Protocol)

Open Data Protocol (OData) is an open protocol that allows the creation and consumption of queryable and interoperable Web service APIs in a standard way. Microsoft initiated OData in 2007.Versions 1.0, 2.0, and 3.0 are released under the Microsoft Open Specification Promise. Version 4.0 was standardized at OASIS.

The protocol enables the creation and consumption of HTTP-based Web APIs, which allow Web clients to publish and edit resources, identified using URLs and defined in a data model, using simple HTTP messages. OData shares some similarities with JDBC and with ODBC; like ODBC, OData is not limited to relational databases.

[https://devblogs.microsoft.com/odata/up-running-w-odata-in-asp-net-6/](https://devblogs.microsoft.com/odata/up-running-w-odata-in-asp-net-6/)

### gRPC

[https://grpc.io](https://grpc.io/)

gRPC is an open-source API architecture and system governed by the Cloud Native Computing Foundation. It's based on the Remote Procedure Call (RPC) model. While the RPC model is broad, gRPC is a specific implementation. [https://aws.amazon.com/compare/the-difference-between-grpc-and-rest](https://aws.amazon.com/compare/the-difference-between-grpc-and-rest)

gRPC (recursive acronym for gRPC Remote Procedure Calls) is a cross-platform high-performance remote procedure call (RPC) framework. gRPC was initially created by Google, but is open source and is used in many organizations. Use cases range from microservices to the "last mile" of computing (mobile, web, and Internet of Things). gRPC uses HTTP/2 for transport, Protocol Buffers as the interface description language, and provides features such as authentication, bidirectional streaming and flow control, blocking or nonblocking bindings, and cancellation and timeouts. It generates cross-platform client and server bindings for many languages. Most common usage scenarios include connecting services in a microservices style architecture, or connecting mobile device clients to backend services [https://en.wikipedia.org/wiki/GRPC](https://en.wikipedia.org/wiki/GRPC)

### SOAP

[https://en.wikipedia.org/wiki/SOAP](https://en.wikipedia.org/wiki/SOAP)

SOAP (formerly an acronym for Simple Object Access Protocol) is a messaging protocol specification for exchanging structured information in the implementation of web services in computer networks. It uses XML Information Set for its message format, and relies on application layer protocols, most often Hypertext Transfer Protocol (HTTP), although some legacy systems communicate over Simple Mail Transfer Protocol (SMTP), for message negotiation and transmission.

SOAP allows developers to invoke processes running on different operating systems (such as Windows, macOS, and Linux) to authenticate, authorize, and communicate using Extensible Markup Language (XML). Since Web protocols like HTTP are installed and running on practically all operating systems, SOAP allows clients to invoke web services and receive responses independent of language and platforms.

## Integration data format (popular)

### JSON

[https://en.wikipedia.org/wiki/JSON](https://en.wikipedia.org/wiki/JSON)

JSON (JavaScript Object Notation, pronounced /ˈdʒeɪsən/; also /ˈdʒeɪˌsɒn/) is an open standard file format and data interchange format that uses human-readable text to store and transmit data objects consisting of attribute--value pairs and arrays (or other serializable values). It is a common data format with diverse uses in electronic data interchange, including that of web applications with servers.

JSON is a language-independent data format. It was derived from JavaScript, but many modern programming languages include code to generate and parse JSON-format data. JSON filenames use the extension .json.

### XML {\#page-content}

[https://en.wikipedia.org/wiki/XML](https://en.wikipedia.org/wiki/XML) Extensible Markup Language (XML) is a markup language and file format for storing, transmitting, and reconstructing arbitrary data. The design goals of XML emphasize simplicity, generality, and usability across the Internet. It is a textual data format with strong support via Unicode for different human languages. Although the design of XML focuses on documents, the language is widely used for the representation of arbitrary data structures such as those used in web services.

Several schema systems exist to aid in the definition of XML-based languages, while programmers have developed many application programming interfaces (APIs) to aid the processing of XML data.

#### XPath

XPath stands for XML Path Language. It uses a non-XML syntax to provide a flexible way of addressing (pointing to) different parts of an XML document. It can also be used to test addressed nodes within a document to determine whether they match a pattern or not.

[https://en.wikipedia.org/wiki/XPath](https://en.wikipedia.org/wiki/XPath)
If a path begins with a '/' character, then it represents the absolute path to the specified element. If the path begins with //, then all document elements that match the specified pattern will be selected.

./ current context

.// all elements of the current context

The '\*' character indicates that all elements matching the path before it should be selected.

Attributes are identified by the @ prefix.

The name() function returns the name of the element. The starts-with() function returns true if the string of the first argument begins with the string of the second argument. The contains() function returns true if the string in the first argument contains the string in the second.

[https://msdn.microsoft.com/ru-ru/library/ms256086(v=vs.120).aspx](<https://msdn.microsoft.com/ru-ru/library/ms256086(v=vs.120).aspx>)

|              Expression              |                                                                                        Refers to                                                                                         |
|--------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ./author                             | All \<author\> elements of the current context. Note that this is equivalent to the expression on the next line.                                                                         |
| author                               | All \<author\> elements of the current context.                                                                                                                                          |
| first. name                          | All \<first.name\> elements of the current context.                                                                                                                                      |
| /bookstore                           | The document element (\<bookstore\>) of this document.                                                                                                                                   |
| //author                             | All \<author\> elements of a given document.                                                                                                                                             |
| book\[/bookstore/@specialty=@style\] | All \<book\> elements for which the value of the style attribute is equal to the value of the specialty attribute of the \<bookstore\> element of the document's root node.              |
| author/first-name                    | All \<first-name\> elements that are children of the \<author\> element.                                                                                                                 |
| bookstore//title                     | All \<title\> elements at the first or deeper levels of the \<bookstore\> element (descendants of an arbitrary level). Notice the difference from the expression on the next line.       |
| bookstore/\*/title                   | All \<title\> elements that are "grandchildren" of \<bookstore\> elements.                                                                                                               |
| bookstore//book/excerpt//emph        | All \<emph\> elements anywhere within \<excerpt\> elements that are children of \<book\> elements anywhere within a \<bookstore\> element.                                               |
| .//title                             | All \<title\> elements at the first or deeper levels of the current context. Note that this is the only situation where dot notation is required.                                        |
| author/\*                            | All elements that are children of \<author\> elements.                                                                                                                                   |
| book/\*/last-name                    | All \<last-name\> elements that are "grandchildren" of \<book\> elements.                                                                                                                |
| \*/\*                                | All elements are "grandchildren" of the current context.                                                                                                                                 |
| \*\[@specialty\]                     | All elements with the specialty attribute.                                                                                                                                               |
| @style                               | The name of the style attribute of the current context.                                                                                                                                  |
| price/@exchange                      | The exchange attribute of \<price\> elements in the current context.                                                                                                                     |
| price/@exchange/total                | Returns an empty set of nodes because the attributes do not contain children. Such an expression is not prohibited by the XPath language grammar, but strictly speaking it is not valid. |
| book\[@style\]                       | All \<book\> elements with style attributes in the current context.                                                                                                                      |
| book/@style                          | The style attribute on all \<book\> elements in the current context.                                                                                                                     |
| @\*                                  | All context attributes of the current element.                                                                                                                                           |
| ./first-name                         | All \<first-name\> elements of the current context. Note that this is equivalent to the expression on the next line.                                                                     |
| first-name                           | All \<first-name\> elements of the current context.                                                                                                                                      |
| author\[1\]                          | All \<author\> elements in the context of the current node.                                                                                                                              |
| author\[first-name\]\[3\]            | The third \<author\> element, which has a \<first-name\> child element.                                                                                                                  |
| my:book                              | The \<book\> element from the my namespace.                                                                                                                                              |
| my:\*                                | All elements from the namespace my.                                                                                                                                                      |
| @my:\*                               | All attributes from the my namespace (this does not include unqualified attributes belonging to elements from the my namespace).                                                         |

|      Expression       |                                              Refers to                                               |
|-----------------------|------------------------------------------------------------------------------------------------------|
| x/y\[1\]              | The first \<y\> child of every \<x\> element. This is equivalent to the expression on the next line. |
| x/y\[position() = 1\] | The first \<y\> child of every \<x\> element.                                                        |
| (x/y)\[1\]            | The first \<y\> element of the entire set of \<y\> elements that are children of \<x\> elements.     |
| x\[1\]/y\[2\]         | The second child \<y\> element of the first \<x\> element.                                           |

|                 Expression                  |                                                                            Refers to                                                                            |
|---------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------|
| book\[last()\]                              | The last \<book\> element in the context of the current node.                                                                                                   |
| book/author\[last()\]                       | The last child \<author\> element of each \<book\> element in the context of the current node.                                                                  |
| (book/author)\[last()\]                     | The last \<author\> element of the entire set of \<author\> elements that are children of \<book\> elements in the context of the current node.                 |
| book\[excerpt\]                             | All \<book\> elements that contain at least one child \<excerpt\> element.                                                                                      |
| book\[excerpt\]/title                       | All \<title\> elements that are children of \<book\> elements and contain at least one child \<excerpt\> element.                                               |
| book\[excerpt\]/author\[degree\]            | All \<author\> elements that contain at least one child \<degree\> element and are children of \<book\> elements that contain at least one \<excerpt\> element. |
| book\[author/degree\]                       | All \<book\> elements that have child \<author\> elements, which in turn have at least one child \<degree\> element.                                            |
| author\[degree\]\[award\]                   | All \<author\> elements that contain at least one \<degree\> element and at least one \<award\> element.                                                        |
| author\[degree and award\]                  | All \<author\> elements that contain at least one \<degree\> element and at least one \<award\> element.                                                        |
| author\[(degree or award) and publication\] | All \<author\> elements that contain at least one \<degree\> or \<award\> child element and at least one \<publication\> child element.                         |

## Api definition

### Overview

[https://en.wikipedia.org/wiki/Data\_modeling](https://en.wikipedia.org/wiki/Data_modeling)

References:

[https://twirl.github.io/The-API-Book/API.en.html](https://twirl.github.io/The-API-Book/API.en.html) Sergey Konstantinov. The API.

### OpenAPI

[https://www.openapis.org/](https://www.openapis.org/) The OpenAPI Specifications provide a formal standard for describing HTTP APIs. This allows people to understand how an API works, how a sequence of APIs work together, generate client code, create tests, apply design standards, and much, much more.

The OpenAPI Specification, previously known as the Swagger Specification, is a specification for a machine-readable interface definition language for describing, producing, consuming and visualizing web services. Originally developed to support the Swagger framework, it became a separate project in 2015, overseen by the OpenAPI Initiative, an open-source collaboration project of the Linux Foundation [https://en.wikipedia.org/wiki/OpenAPI\_Specification](https://en.wikipedia.org/wiki/OpenAPI_Specification)

OpenAPI Tools [https://openapi.tools/](https://www.youtube.com/redirect?event=video_description&redir_token=QUFFLUhqa0VEZmFCUWlNbXRGYUdVX1hkY19jM1FST1o2d3xBQ3Jtc0tuVHRoRlUzdlpLM1J3dmpNT0Z1enRNZGI4dUpJeXlIdkwyWW8weGNLNHl4WWFkRWNZTVVlc25SU0U3cjBtdnJGdVVQSEJjY0RXV2g2TmtZQW1YaVBWbm1XSE1RZEFydHduVkhPRGV3WUNCTUdmWk1zTQ&q=https%3A%2F%2Fopenapi.tools%2F&v=W9sYAdiLnt8)

### TypeSpec

[https://typespec.io/](https://typespec.io/) API-First for developers. With TypeSpec, remove the handwritten files that slow you down, and generate standards-compliant API schemas in seconds.

A New Language Developed by Microsoft. TypeSpec is a language that generates other API description languages, client and service code, documentation, and other resources. TypeSpec is used to describe cloud service APIs. Here, GraphQL, REST, gRPC, and other common APIS forms can be described by TypeSpec's extremely flexible core language primitives. [https://radixweb.com/blog/typespec-language-for-api-development](https://radixweb.com/blog/typespec-language-for-api-development)

### JSON:API

A specification for building APIs in JSON

[https://jsonapi.org/](https://jsonapi.org/)

## References

[https://en.wikipedia.org/wiki/Category:Enterprise\_application\_integration](https://en.wikipedia.org/wiki/Category:Enterprise_application_integration) Category:Enterprise application integration

[https://en.wikipedia.org/wiki/Category:Message-oriented\_middleware](https://en.wikipedia.org/wiki/Category:Message-oriented_middleware) Category:Message-oriented middleware

[https://aosabook.org/en/v2/distsys.html](https://aosabook.org/en/v2/distsys.html) Kate Matsudaira The Architecture of Open Source Applications (Volume 2) Scalable Web Architecture and Distributed Systems

[https://www.youtube.com/watch?v=o7ogFTMJW1A](https://www.youtube.com/watch?v=o7ogFTMJW1A)
