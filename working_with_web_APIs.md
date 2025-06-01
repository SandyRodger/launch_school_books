# [Working with Web APIs](https://launchschool.com/books/working_with_apis)

## Introduction
### What this Book Covers
- Web 2.0 web applications focus on user participation and content-creation.
- APIs allow this by being software one can plug into one's web app.

- We're covering the basics here (and in the associated course? - JS235?):
  -  what is it
  -  How to interact with them
  -  How to build your own

## [Preparations](https://launchschool.com/books/working_with_apis/read/preparations)

- `brew install httpie`
- `http --version` -> 3.2.4
- https://www.postman.com/downloads/

#### HTTPie Option Reference

- `-p`
- `-a`
- `--help`
  
## [Using Postman](https://launchschool.com/books/working_with_apis/read/using_postman#makingarequest)

- It's like a specialised web-browser.
- `www.google.com/search`
- The API example uses DUckDuckGo, but I have blocked that website, so ChatGPT provided the following alternatives:
  - `https://en.wikipedia.org/w/api.php?action=opensearch&search=pistachios&limit=5&format=json`
  - `https://itunes.apple.com/search?term=pistachios&limit=5`
- APIs can be accesed using secure URLs like web-pages.

### Checking the Weather
- This brings up an important point about working with APIs: it is very important to read any documentation for the API in order to be able to interpret the values in a response.

### Summary

- postman makes it easy to make http requests from a web browser
- because it runs in a web-browser, Postman has few dependencies and is easy to install on almost any computer.

## Defining API
### [What is an API?](https://launchschool.com/books/working_with_apis/read/defining_api#whatisanapi)

- Application Programming Interface: provides a way for computer systems to interact with each other
- Every programming language has a built-in API that is used to write programs.
- Mobile devices provide APIs to provide access to location etc.
- Practically everything has an API. What they all do is provide functionality for use by another program.

### [Web APIs](https://launchschool.com/books/working_with_apis/read/defining_api#webapis)

- A type of API that are built with web-technologies and work similarly to the web itself.

### [Provider and Consumer](https://launchschool.com/books/working_with_apis/read/defining_api#provider_and_consumer)

- We must distinguish between the system the API belongs to and the external service that will use the API.
  - API PROVIDER: the system that provides the API for other parites to use. For instance HitHub is the provider of the GitHub API.
  - An API consumer is the system taht uses the API ti accomplish some work. When you look at the weather on your phone it is running a program which is consuming a weather API to retrieve forcast data.

- in this boook we will be the manual consumers of the web store API. 
### [What about Clients and Servers?](https://launchschool.com/books/working_with_apis/read/defining_api#clientsandservers)

- forget the image of the large server farm and the individual mobile phone as the client, we just mean the server as the API provider and the client as the consumer.

### [Summary](https://launchschool.com/books/working_with_apis/read/defining_api#summary)

- Web APIs allow one system to interact with another over HTTP
- The system offering the API for use by the others is the provider
- The system interacting with the API to accomplish a goal in the consumer
- It is best to use the terms provider and consumer over client and server.
  
## [What APIs Can Do](https://launchschool.com/books/working_with_apis/read/what_apis_can_do)

### [Sharing Data](https://launchschool.com/books/working_with_apis/read/what_apis_can_do#sharingdate)

- share data between systems1

### [Enabling Automation](https://launchschool.com/books/working_with_apis/read/what_apis_can_do#enablingautomation)

- HatCo example
- "APIs allow users of a service to make use of it in new and useful ways."

### [Leverage Existing Services](https://launchschool.com/books/working_with_apis/read/what_apis_can_do#leverageexistingservices)

- "APIs enable application developers to build their applications on top of a variety of other specialized systems, allowing them to focus on their actual objectives and not worry about all the complexities of every part of the system."

### [Summary](https://launchschool.com/books/working_with_apis/read/what_apis_can_do#summary)

- APIs break the walls beween systems allowing them to share data.
- APIs provide an escape hatch; enabling service users to customise the software's beyaviour or integrate it into other sytems if required.
- Many modern web applications provide an API that allows developers to integrate their own code with these applications, taking advantage of the services' functionality in their own apps.

## [Accessibility](https://launchschool.com/books/working_with_apis/read/accessibility)

### [Public and Private](https://launchschool.com/books/working_with_apis/read/accessibility#publicandprivate)

##### Public APIs
- Insta, facebook, Twitter -> they all got em.
##### Private APIs
- GOogle search page. Don't try and call private APIs. It's sometimes doable, but generally a bad idea.
- Companies often gain an advantage in making their APIs public.

### [Terms and conditions](https://launchschool.com/books/working_with_apis/read/accessibility#termsandconditions)

- **Restrictions** You should understand waht restrictions does the API place on your use of its data. For instance data from the Amazon Product Advertising API is only available to Amazon Associates.
- **Is the API exposing any personal data?** Many social apops allow acces to a user;'s personal info, but by accessing it you are thaking the responsibility of keeping it secure.
-  **rate limits** Many APIs limit how many requests can be sent from a single user/app. Such restrictons will impact how you design your app.

### [Summary](https://launchschool.com/books/working_with_apis/read/accessibility#summary)


- APIs come in 2 flavours: public and private. You'll mainly be using pulics, private's usually when it's your own.
- You usually have to accept terms of the API provider

## [A Review of HTTP](https://launchschool.com/books/working_with_apis/read/a_review_of_http)

### [Request and Response](https://launchschool.com/books/working_with_apis/read/a_review_of_http#requestandresponse)


- Web APIs work wiht HyperTextTransfer Protocol -> just like websites/browsers/servers.
- request-response pattern. Remember this?
- IPAPI (PrettyBallsy)
  - API access key: 7c8917a2deabd924800fb9e0a6d51183
- `http http://api.ipapi.com/161.185.160.93?access_key=7c8917a2deabd924800fb9e0a6d51183 --json`

```
HTTP/1.1 200 OK
Access-Control-Allow-Headers: *
Access-Control-Allow-Methods: GET, POST, HEAD, OPTIONS
Access-Control-Allow-Origin: *
Cf-Cache-Status: DYNAMIC
Cf-Ray: 948112150ae0cc8d-MAN
Connection: keep-alive
Content-Type: application/json
Date: Fri, 30 May 2025 20:44:38 GMT
Nel: {"success_fraction":0,"report_to":"cf-nel","max_age":604800}
Report-To: {"endpoints":[{"url":"https:\/\/a.nel.cloudflare.com\/report\/v4?s=P7ergkYr%2BJnDuMkUMVCCCyNeL9OTUKK8ZSFVnEaQbId8InceSc61Y2eaOwjb4cvbodD6WyRrFAsv7PfY%2FX8rzAlfWJsr9OqyIx288VknBmb0FAeFfcDne4xtYE165CE%3D"}],"group":"cf-nel","max_age":604800}
Server: cloudflare
Server-Timing: cfL4;desc="?proto=TCP&rtt=15293&min_rtt=15293&rtt_var=7646&sent=1&recv=3&lost=0&retrans=0&sent_bytes=0&recv_bytes=215&delivery_rate=0&cwnd=225&unsent_bytes=0&cid=0000000000000000&ts=0&x=0"
Transfer-Encoding: chunked
X-Apilayer-Transaction-Id: 10da26df-46b4-4957-b77f-81fc2d67d7af
```

- Break-down:
  - status code: HTTP/1.1 200 OK
- 2xx is good
- 3xx is successful, but the response to the request is somewhere else
- 4xx means the client's made a mistake
- 5xx means the server's encountered an error, usually they screwed up, rather than the client.

### [Headers](https://launchschool.com/books/working_with_apis/read/a_review_of_http#headers)

- for example:

```
CF-Cache-Status: DYNAMIC
CF-RAY: 7694e9094d32ef9c-PDX
Connection: keep-alive
Content-Encoding: gzip
Content-Type: application/json
Date: Sun, 13 Nov 2022 04:54:35 GMT
NEL: {"success_fraction":0,"report_to":"cf-nel","max_age":604800}
Report-To: {"endpoints":[{"url":"https:\/\/a.nel.cloudflare.com\/report\/v3?s=VJQHe9u15PD8yXpSY0ZwfioL2qi8iHUOoiQLdEzMKnAnIrmmrtM6caxSquhaKkJuzMVBs3GHty42saK3qQsqqgjBSTuw0yeGlgAmXaJ3vItVuCcntg4vPOUfvQC%2FeyUOEmdN0C9DqoxDMqSA"}],"group":"cf-nel","max_age":604800}
Server: cloudflare
Transfer-Encoding: chunked
access-control-allow-headers: *
access-control-allow-methods: GET, POST, HEAD, OPTIONS
access-control-allow-origin: *
alt-svc: h3=":443"; ma=86400, h3-29=":443"; ma=86400
x-apilayer-transaction-id: 113aa789-ec14-4759-bb75-972b61f7b70f
x-increment-usage: 1
x-quota-limit: 1000
x-quota-remaining: 996
x-request-time: 0.031
```

- of which the content type is the most important:
  - `Content-Type: application/json`

### [Body](https://launchschool.com/books/working_with_apis/read/a_review_of_http#body)

- getting sleepy

### [Summary](https://launchschool.com/books/working_with_apis/read/a_review_of_http#summary)

- Web APIs are buolt on top of HTTP the technology that makes the web work
- HTTP responses have 3 main parts: status code, headers and body
- The conten-type header describes the format of the response body

## [A Review of URLs](https://launchschool.com/books/working_with_apis/read/a_review_of_urls)

### [URL or URI](https://launchschool.com/books/working_with_apis/read/a_review_of_urls#url_or_uri)

- URI: uniform resource Identifier: this identifies a resource. **These can be anywhere**
  - analogous to social security number
- URL: Uniform resource locator: a web resource with a specified locaton on a computer network.
  -  analogous to someone's street address
  -  ALso unique, so you could say a URL is a type of URI.
-  IF YOU ARE WORKING WITH RESOURCES ON THE INTERNET USE URL

### The parts of a URL

- Scheme: https
- `://`
- hostname
- optional colon and port: `:81` (uncommon with APIs)
- the path to the resource, like `/api/v1/pages/1`
- An optional query string: `?=query=term`

### [Identifiers in Paths](https://launchschool.com/books/working_with_apis/read/a_review_of_urls#identifiers_in_paths)

- `/products/:id` , where :id is a place-holder to be filled with a value.
- Nested paths are also a thing: `/products/:product_id/comments/:id`

### [Summary](https://launchschool.com/books/working_with_apis/read/a_review_of_urls#summary)

- Working with APIS, involves working with URLs
- URLs represent where a resource is and how it can be accessed.
- URLs typically contain a:
  - Scheme
  - hostname
  - path
  - sometimes a query string
- Paths can include placeholders when they are written generically

## [Media Types](https://launchschool.com/books/working_with_apis/read/media_types)

- The internet has shared markup languages and data formats to facilitate communication. HTML is an example of this. Almost all devices can read HTML and display it.
- HTML is one of many different **media types** (AKA content types sometimes AKA MIME types)
- `Content-Type: text/html` -> this tells the browser to interpret the content as HTML rather than render it graphically on the screen.
- `charset`
- `http --headers www.google.com`
- photos are returned as `image/jpeg`
  - example: `http --headers https://c2.staticflickr.com/4/3913/15095210318_930069f3d6_c.jpg`

### Data-serialization

- APIs allow systems to communicate by exchanging structured data. The structure of these is **data serialization format**
- Example with the black circle
- A "vector graphics program"
- save a representation of the circe with some SVG code(?)

```html
<svg viewBox="0 0 55 54">
  <circle cx="32.5" cy="22" r="21.3" fill="black"/>
</svg>
```

### XML

- Extensible Markup language
- stricter than HTML
- example:

```javascript
  <address>
    <street>1600 Pennsylvania Ave NW</street>
    <city>Washington</city>
    <state>DC</state>
    <zipcode>20500</zipcode>
    <country>Unites States</country>
</address>
```

### [JSON](https://launchschool.com/books/working_with_apis/read/media_types#json)

- a simple JSON document is used to represent key and value pairs:

```json
{
  "street": "1600 Pennsylvania Ave NW",
  "city": "Washington",
  "state": "DC",
  "zipcode": "20500",
  "country": "United States"
}
```

- this book we'll only use JSON

### [Summary](https://launchschool.com/books/working_with_apis/read/media_types#summary)

- media-types describe the format of a response's body
- media types are represented in an http response's `content-type` header and as a result are soemtimes referred to as content types.
- data-serialization provies a common way for systems to pass data to each other, with a guarantee that each system will be able to understand the data.
- JSON is the most popular media type for web APIs.

## [REST and CRUD](https://launchschool.com/books/working_with_apis/read/rest_and_crud)

### [What is REST?](https://launchschool.com/books/working_with_apis/read/rest_and_crud#rest)
- representational State Transfer
- representational => we send a copy
- State transfer: how HTTP is a stateless protocol, so the servers don't know anything at all about the clients and everything the server needs to process the request is included in the state itself.

- example of deleting a social media profile. The same actions could be performed by an API. Differences:
  - HTML forms must be loaded before they cab be submitted. Not so for APIs, they don't have forms. Therefore we can lose the initial GET request.
  - HTML forms only support 2 of the many HTTP methods, GET and POST. APIs are able to take advantage of all HTTP methods so they're clearer.
  - REST encompasses everything you would like to do with 'what' and 'how'.
    - what  resource is being brought into play?
    - how are we changing / interacting with it?

### [CRUD](https://launchschool.com/books/working_with_apis/read/rest_and_crud#crud)

- the 4 things you can do with a resource.
  - POST - create
  - GET - post
  - PUT - update
  - DELETE - delete
- if you know which action you want to take, you probably know which method to use.
-  By following REST conventions, API designers have fewer decisions to make about how to build an API and API consumers have fewer questions to answer before using one

### [A RESTful API Template](https://launchschool.com/books/working_with_apis/read/rest_and_crud#restfulapitemplate)

- template for any resource:

<img width="713" alt="Screenshot 2025-05-31 at 17 46 45" src="https://github.com/user-attachments/assets/39fc70d5-79fb-4b75-8add-e7040c877d57" />

- by following REST conventions most of the decisions a designer has to make turn into: What resources will be exposed?
- A lot of the perspective shift involves changing verb-based language into noun based ie:
  - (deposit $100 into this account) -> (create a new transaction with an amount of $100 for this account)
 
### [Resource-Oriented Thinking](https://launchschool.com/books/working_with_apis/read/rest_and_crud#resourceorientedthinking)

- examples:

<img width="701" alt="Screenshot 2025-05-31 at 17 50 54" src="https://github.com/user-attachments/assets/7b6ec1ff-a13c-4155-9ff9-472ff39f2647" />

- **singular resource or singleton resource**

### Conventions, not Rules
### Summary

- REST is a set of conventions about how to build APIs.
- RESTful APIs consist of CRUD actions on a resource
- By limiting actions to CRUD, REST requires thinking in a resource-oriented way.
- It is worth being as RESTful as possible, but there are times when it is not the best solution.

# WORKING WITH AN API
## [Fetching Resources](https://launchschool.com/books/working_with_apis/read/fetching_resources#serversetup)

### [Server setup](https://launchschool.com/books/working_with_apis/read/fetching_resources#serversetup)
- [apiculture](https://apiculture-n0y1.onrender.com/)
- apiculture-n0y1

### [Fetching a Resource](https://launchschool.com/books/working_with_apis/read/fetching_resources#fetchingaresource)

- `http GET https://apiculture-n0y1.onrender.com/v1/products/1`

```
HTTP/1.1 200 OK
CF-RAY: 9488393f3fe0b396-MAN
Connection: keep-alive
Content-Encoding: gzip
Content-Type: application/json
Date: Sat, 31 May 2025 17:34:44 GMT
Server: cloudflare
Transfer-Encoding: chunked
alt-svc: h3=":443"; ma=86400
cf-cache-status: DYNAMIC
rndr-id: af83d137-14e2-4bf4
status: 200 OK
vary: Origin, Accept-Encoding
x-render-origin-server: Render

{
    "id": 1,
    "name": "Red Pen",
    "price": 100,
    "sku": "redp100"
}
```
### [What is a Resource?](https://launchschool.com/books/working_with_apis/read/fetching_resources#what_is_a_resource)

-  the representation of some grouping of data.
-  anything an API has to deal with

### [Fetching a collection](https://launchschool.com/books/working_with_apis/read/fetching_resources#fetching_a_collection)

- `http GET https://apiculture-n0y1.onrender.com/v1/products`

```
[
    {
        "id": 1,
        "name": "Red Pen",
        "price": 100,
        "sku": "redp100"
    },
    {
        "id": 2,
        "name": "Blue Pen",
        "price": 100,
        "sku": "blup100"
    },
    {
        "id": 3,
        "name": "Black Pen",
        "price": 100,
        "sku": "blap100"
    }
]
```

### [Elements and Collections](https://launchschool.com/books/working_with_apis/read/fetching_resources#elements_and_collection)

- There are 2 elements involved in the use of RESTful APIs:
  -  elements (could be `/api/blog/posts/1`)
  -  collections (could be `/api/blog/posts`)

#### How to know if a URL is for a collection or an element?

-  it is best to reference the API's official documentation.
- often there is none, so:
  - Collection clues:
    - path ends in plural word => `example.com/products`
    - Response body contains multiple elements
  - single element clues:
    - path ends in plural word - slash - identifier
    - Response body contains single element

### [Summary](https://launchschool.com/books/working_with_apis/read/fetching_resources#summary)

- APIs provide access to single resources (elements) or groups of resources (collections).
- The path for an element is usually the path for its collection, plus an identifier for that resource.

## [Requests in Depth](https://launchschool.com/books/working_with_apis/read/requests_in_depth)

### [GET and POST](https://launchschool.com/books/working_with_apis/read/requests_in_depth#get_and_post)

- all requests made to web-servers start with an HTTP method (sometimes called a verb)
- For a long time web-browsers only supported GET and POST

### [Parts of a Request](https://launchschool.com/books/working_with_apis/read/requests_in_depth#parts_of_a_request)

- `http --print H GET https://apiculture-n0y1.onrender.com/v1/products/1`
- `Accept: */*` -> specifies waht media types the client will accept. This means any type. It's better to be more explicit.
- We want JSON, so we need to iinclude `application/json` =>

`http --print=H GET https://apiculture-n0y1.onrender.com/v1/products/1 Accept:application/json`

```
GET /v1/products/1 HTTP/1.1
Accept: application/json
Accept-Encoding: gzip, deflate
Connection: keep-alive
Host: apiculture-n0y1.onrender.com
User-Agent: HTTPie/3.2.4
```

### [Summary](https://launchschool.com/books/working_with_apis/read/requests_in_depth#summary)

- HTTP requests include a path, method, headers and body.
- The **Accept** header tells the provider what media types can be used to respond to the request

## [Creating Resources](https://launchschool.com/books/working_with_apis/read/creating_resources)

- There are also many applications that provide specialized reporting for some aspect of another system such as social networking sites

### [HTTP Request Side Effects](https://launchschool.com/books/working_with_apis/read/creating_resources#http_request_side_effects)

- GET requests should not alter resources, but there can be side-effects. For example a hit-counter. So consider this when creating resources.

### [Creating a resource](https://launchschool.com/books/working_with_apis/read/creating_resources#creating_a_resource)

- If you're making changes it's read and write, if not it's read-only
- Form submission is always POST
- We're going to try adding a resource to our web-page, but for this we'll need authentication.

`http POST https://apiculture-n0y1.onrender.com/v1/products name="Purple Pen" sku="purp100" price:=100` =>

```
HTTP/1.1 401 Unauthorized
CF-RAY: 948dcc2c7bf6eb1c-MAN
Connection: keep-alive
Content-Type: application/json
Date: Sun, 01 Jun 2025 09:48:50 GMT
Server: cloudflare
Transfer-Encoding: chunked
alt-svc: h3=":443"; ma=86400
cf-cache-status: DYNAMIC
rndr-id: dfe970ae-2f0a-4b3c
status: 401 Unauthorized
vary: Origin, Accept-Encoding
x-render-origin-server: Render

{
    "message": "Must pass credentials in Authentication header.",
    "status_code": 401
}
```

- Our web store uses token-based authentication, which is a common way to secure API endpoints

- `http POST https://apiculture-n0y1.onrender.com/v1/products Authorization:"token AUTH_TOKEN" name="Purple Pen" sku="purp100" price:=100`

```
HTTP/1.1 201 Created
CF-RAY: 948dd1821fb83c84-MAN
Connection: keep-alive
Content-Type: application/json
Date: Sun, 01 Jun 2025 09:52:29 GMT
Server: cloudflare
Transfer-Encoding: chunked
alt-svc: h3=":443"; ma=86400
cf-cache-status: DYNAMIC
rndr-id: 921c8735-db24-4361
status: 201 Created
vary: Origin, Accept-Encoding
x-render-origin-server: Render

{
    "id": 4,
    "name": "Purple Pen",
    "price": 100,
    "sku": "purp100"
}
```

- Many APIs use more sophisticated authentication means like OAuth or API keys

### [Handling Errors](https://launchschool.com/books/working_with_apis/read/creating_resources#handling_errors)

- Common errors and what you should do with them:

##### Missing or Invalid Parameters
  - example: `http POST https://apiculture-n0y1.onrender.com/v1/products Authorization:"token AUTH_TOKEN"`

```
HTTP/1.1 422 Unprocessable Entity
CF-RAY: 948ddce488172204-MAN
Connection: keep-alive
Content-Type: application/json
Date: Sun, 01 Jun 2025 10:00:15 GMT
Server: cloudflare
Transfer-Encoding: chunked
alt-svc: h3=":443"; ma=86400
cf-cache-status: DYNAMIC
rndr-id: 9d3a3f07-f7f4-487a
status: 422 Unprocessable Entity
vary: Origin, Accept-Encoding
x-render-origin-server: Render

{
    "message": "Name is missing, sku is missing, price is missing",
    "status_code": 422
}
```

- status 422 -> unprocessable entity

##### Missing resources

- http GET https://apiculture-n0y1.onrender.com/v1/products/42

```
HTTP/1.1 404 Not Found
CF-RAY: 948de0eaffa32dd8-MAN
Connection: keep-alive
Content-Encoding: gzip
Content-Type: application/json
Date: Sun, 01 Jun 2025 10:03:00 GMT
Server: cloudflare
Transfer-Encoding: chunked
alt-svc: h3=":443"; ma=86400
cf-cache-status: DYNAMIC
rndr-id: 93277252-686b-4ce7
status: 404 Not Found
vary: Origin, Accept-Encoding
x-render-origin-server: Render

{
    "message": "Couldn't find WebStore::Product with 'id'=42",
    "status_code": 404
}
```

##### Authentication

- 401, 403, 404

##### Incorrect Media Type

- HTTPie automatically converts media-types into JSON because that's the most common.
- The `HBhb` value in the following tells HTTPie to print out the heaeders and body for both request and response:

`http --print HBhb POST https://apiculture-n0y1.onrender.com/v1/products Authorization:"token AUTH_TOKEN"`

```
POST /v1/products HTTP/1.1
Accept: */*
Accept-Encoding: gzip, deflate
Authorization: token AUTH_TOKEN
Connection: keep-alive
Content-Length: 0
Host: apiculture-n0y1.onrender.com
User-Agent: HTTPie/3.2.4



HTTP/1.1 422 Unprocessable Entity
CF-RAY: 948de7582935d85e-MAN
Connection: keep-alive
Content-Type: application/json
Date: Sun, 01 Jun 2025 10:07:23 GMT
Server: cloudflare
Transfer-Encoding: chunked
alt-svc: h3=":443"; ma=86400
cf-cache-status: DYNAMIC
rndr-id: 67a3f66e-439d-44b7
status: 422 Unprocessable Entity
vary: Origin, Accept-Encoding
x-render-origin-server: Render

{
    "message": "Name is missing, sku is missing, price is missing",
    "status_code": 422
}
```

- note: content type is application/JSON and body is JSON

##### Rate limiting

- It's possible an API will receive too many requests in a short period of time.
- Most APIs address this problem by enforcing "rate limiting".
- These usually return 403 forbidden

##### Server Errors

- The above are all client errors. They have the code 5xx.
- possible causes:
  -  a bug in server implementation
  -  Hardward problem
  -  Unforseen error (same as first point?)
  - Sometimes a 5xx error is returned when a client error would be more fitting.

### [Summary](https://launchschool.com/books/working_with_apis/read/creating_resources#summary)

- create resources with POST
- requests need to include all required parameters and use the proper media type
- responses to failed requests will often contain information about the cause of failure

## [More HTTP Methods](https://launchschool.com/books/working_with_apis/read/more_http_methods)

### [Updating a resource](https://launchschool.com/books/working_with_apis/read/more_http_methods#updating_a_resource)

- fetch all products to see what's there:
  - http GET https://apiculture-n0y1.onrender.com/v1/products

```
HTTP/1.1 200 OK
CF-RAY: 948dfae50fed9b32-MAN
Connection: keep-alive
Content-Encoding: gzip
Content-Type: application/json
Date: Sun, 01 Jun 2025 10:20:44 GMT
Server: cloudflare
Transfer-Encoding: chunked
alt-svc: h3=":443"; ma=86400
cf-cache-status: DYNAMIC
rndr-id: 052be07c-cc0a-45a0
status: 200 OK
vary: Origin, Accept-Encoding
x-render-origin-server: Render

[
    {
        "id": 1,
        "name": "Red Pen",
        "price": 100,
        "sku": "redp100"
    },
    {
        "id": 2,
        "name": "Blue Pen",
        "price": 100,
        "sku": "blup100"
    },
    {
        "id": 3,
        "name": "Black Pen",
        "price": 100,
        "sku": "blap100"
    },
    {
        "id": 4,
        "name": "Purple Pen",
        "price": 100,
        "sku": "purp100"
    }
]
```

- updating this product will look a lot like creating a new one. Differences are we use PUT instead of POST and the product's path instead of the product collection path. (so /products/1 instead of /products)

- http PUT https://apiculture-n0y1.onrender.com/v1/products/4 Authorization:"token AUTH_TOKEN" price=150
- http PUT https://apiculture-n0y1.onrender.com/v1/products/4 Authorization:"token AUTH_TOKEN" name="New and Improved Purple Pen" sku="newp100"
```
HTTP/1.1 200 OK
CF-RAY: 948e05bafe68eb1d-MAN
Connection: keep-alive
Content-Encoding: gzip
Content-Type: application/json
Date: Sun, 01 Jun 2025 10:28:08 GMT
Server: cloudflare
Transfer-Encoding: chunked
alt-svc: h3=":443"; ma=86400
cf-cache-status: DYNAMIC
rndr-id: 993ab4fc-de79-4d51
status: 200 OK
vary: Origin, Accept-Encoding
x-render-origin-server: Render

{
    "id": 4,
    "name": "Purple Pen",
    "price": 150,
    "sku": "purp100"
}
```

### [Deleting a Resource](https://launchschool.com/books/working_with_apis/read/more_http_methods#deleting_a_resource)

- like fetching a resource, except you use DELETE.
- http DELETE https://apiculture-n0y1.onrender.com/v1/products/4 Authorization:"token AUTH_TOKEN"

```
HTTP/1.1 204 No Content
CF-RAY: 948e0b086ce70757-MAN
Connection: keep-alive
Date: Sun, 01 Jun 2025 10:31:45 GMT
Server: cloudflare
alt-svc: h3=":443"; ma=86400
cf-cache-status: DYNAMIC
rndr-id: 2b6f5725-c07b-4c1a
status: 204 No Content
vary: Origin
x-render-origin-server: Render
```

### [Summary](https://launchschool.com/books/working_with_apis/read/more_http_methods#summary)

- Use HTTP method PUT to update resources.
- Use HTTP method DELETE to delete resources.

# REAL WORLD APIS
## [TMDB API](https://launchschool.com/books/working_with_apis/read/tmdb_api)
### Our Goal

- learn how to interact with this movie-database. How to fetch movie-data and rate the movie

### [Reading Documentation](https://launchschool.com/books/working_with_apis/read/tmdb_api#readingdocumentation)

- First steps fo working with an API:
  - What's the URL:
    - protocol
    - host
    - path
  - what params do I need
  - What auth is required
- we'll look here: https://developer.themoviedb.org/reference/intro/getting-started
- Movies -> details : https://developer.themoviedb.org/reference/movie-details

### [First API Request](https://launchschool.com/books/working_with_apis/read/tmdb_api#firstrequest)

- https://api.themoviedb.org/3/movie/27205
- Inception

```
HTTP/1.1 401 Unauthorized
Alt-Svc: h3=":443"; ma=86400
Cache-Control: public, max-age=300
Connection: keep-alive
Content-Type: application/json; charset=utf-8
Date: Sun, 01 Jun 2025 10:42:38 GMT
Server: openresty
Transfer-Encoding: chunked
Vary: Origin
Via: 1.1 da75aba073a4674b4acba0f7682b0446.cloudfront.net (CloudFront)
X-Amz-Cf-Id: tAF5Q9XlGcfHIkjmRSdLpWpbf6aQV4OXxSmCuikbLlpmaD9cDj_SrQ==
X-Amz-Cf-Pop: LHR50-P2
X-Cache: Error from cloudfront

{
    "status_code": 7,
    "status_message": "Invalid API key: You must be granted a valid key.",
    "success": false
}
```
- need auth.

### [Gaining Access](https://launchschool.com/books/working_with_apis/read/tmdb_api#gainingaccess)

- we won't be using a URL, so use `http://localhost:3000`
- API read-access token:
`eyJhbGciOiJIUzI1NiJ9.eyJhdWQiOiIzMDY5ZjIyNjc4YmJkODliZDRhNmQyY2IwYzI0OWUzNCIsIm5iZiI6MTc0ODc3NDkzMC40NjQsInN1YiI6IjY4M2MzMDEyZTg2NTYzYjgxMWQyMTIxZSIsInNjb3BlcyI6WyJhcGlfcmVhZCJdLCJ2ZXJzaW9uIjoxfQ.5GIHNExqKPBkcsqbcE414OqC3NpEFgMIgB-4QBAC-Tk`
- API key -> `3069f22678bbd89bd4a6d2cb0c249e34`

### [Fetching movie information](https://launchschool.com/books/working_with_apis/read/tmdb_api#fetchingmovieinfo)

- http GET https://api.themoviedb.org/3/movie/27205 \
    "Authorization: Bearer eyJhbGciOiJIUzI1NiJ9.eyJhdWQiOiIzMDY5ZjIyNjc4YmJkODliZDRhNmQyY2IwYzI0OWUzNCIsIm5iZiI6MTc0ODc3NDkzMC40NjQsInN1YiI6IjY4M2MzMDEyZTg2NTYzYjgxMWQyMTIxZSIsInNjb3BlcyI6WyJhcGlfcmVhZCJdLCJ2ZXJzaW9uIjoxfQ.5GIHNExqKPBkcsqbcE414OqC3NpEFgMIgB-4QBAC-Tk"

```
http GET https://api.themoviedb.org/3/movie/27205 \
>     "Authorization: Bearer eyJhbGciOiJIUzI1NiJ9.eyJhdWQiOiIzMDY5ZjIyNjc4YmJkODliZDRhNmQyY2IwYzI0OWUzNCIsIm5iZiI6MTc0ODc3NDkzMC40NjQsInN1YiI6IjY4M2MzMDEyZTg2NTYzYjgxMWQyMTIxZSIsInNjb3BlcyI6WyJhcGlfcmVhZCJdLCJ2ZXJzaW9uIjoxfQ.5GIHNExqKPBkcsqbcE414OqC3NpEFgMIgB-4QBAC-Tk"
HTTP/1.1 200 OK
Alt-Svc: h3=":443"; ma=86400
Cache-Control: public, max-age=6991
Connection: keep-alive
Content-Encoding: gzip
Content-Type: application/json;charset=utf-8
Date: Sun, 01 Jun 2025 10:55:20 GMT
ETag: W/"5d0b668cbd65633dab0f600de60311c1"
Server: openresty
Transfer-Encoding: chunked
Vary: accept-encoding, Origin
Via: 1.1 2a3070b1680e47b1f595c5f66410764a.cloudfront.net (CloudFront)
X-Amz-Cf-Id: hQ-2SmkO927sZyJJrihUil2Ru7BjSdmhHk9j3PoNHyZOdlYFu-MZSA==
X-Amz-Cf-Pop: LHR50-P2
X-Cache: Miss from cloudfront
x-az: us-east-1a
x-memc: HIT
x-memc-age: 18539
x-memc-expires: 6991
x-memc-key: ba0bb4b9033cab23506074980327c2f8
x-task-id: 5ae9ef7c9edb4082a88f27237d27cbc2

{
    "adult": false,
    "backdrop_path": "/8ZTVqvKDQ8emSGUEMjsS4yHAwrp.jpg",
    "belongs_to_collection": null,
    "budget": 160000000,
    "genres": [
        {
            "id": 28,
            "name": "Action"
        },
        {
            "id": 878,
            "name": "Science Fiction"
        },
        {
            "id": 12,
            "name": "Adventure"
        }
    ],
    "homepage": "https://www.warnerbros.com/movies/inception",
    "id": 27205,
    "imdb_id": "tt1375666",
    "origin_country": [
        "US",
        "GB"
    ],
    "original_language": "en",
    "original_title": "Inception",
    "overview": "Cobb, a skilled thief who commits corporate espionage by infiltrating the subconscious of his targets is offered a chance to regain his old life as payment for a task considered to be impossible: \"inception\", the implantation of another person's idea into a target's subconscious.",
    "popularity": 26.3253,
    "poster_path": "/oYuLEt3zVCKq57qu2F8dT7NIa6f.jpg",
    "production_companies": [
        {
            "id": 923,
            "logo_path": "/5UQsZrfbfG2dYJbx8DxfoTr2Bvu.png",
            "name": "Legendary Pictures",
            "origin_country": "US"
        },
        {
            "id": 9996,
            "logo_path": "/3tvBqYsBhxWeHlu62SIJ1el93O7.png",
            "name": "Syncopy",
            "origin_country": "GB"
        },
        {
            "id": 174,
            "logo_path": "/zhD3hhtKB5qyv7ZeL4uLpNxgMVU.png",
            "name": "Warner Bros. Pictures",
            "origin_country": "US"
        }
    ],
    "production_countries": [
        {
            "iso_3166_1": "GB",
            "name": "United Kingdom"
        },
        {
            "iso_3166_1": "US",
            "name": "United States of America"
        }
    ],
    "release_date": "2010-07-15",
    "revenue": 839030630,
    "runtime": 148,
    "spoken_languages": [
        {
            "english_name": "English",
            "iso_639_1": "en",
            "name": "English"
        },
        {
            "english_name": "French",
            "iso_639_1": "fr",
            "name": "Français"
        },
        {
            "english_name": "Japanese",
            "iso_639_1": "ja",
            "name": "日本語"
        },
        {
            "english_name": "Swahili",
            "iso_639_1": "sw",
            "name": "Kiswahili"
        }
    ],
    "status": "Released",
    "tagline": "Your mind is the scene of the crime.",
    "title": "Inception",
    "video": false,
    "vote_average": 8.369,
    "vote_count": 37509
}
```

- non-existant movie test:
  - http GET https://api.themoviedb.org/3/movie/999999999 \
    "Authorization: Bearer eyJhbGciOiJIUzI1NiJ9.eyJhdWQiOiIzMDY5ZjIyNjc4YmJkODliZDRhNmQyY2IwYzI0OWUzNCIsIm5iZiI6MTc0ODc3NDkzMC40NjQsInN1YiI6IjY4M2MzMDEyZTg2NTYzYjgxMWQyMTIxZSIsInNjb3BlcyI6WyJhcGlfcmVhZCJdLCJ2ZXJzaW9uIjoxfQ.5GIHNExqKPBkcsqbcE414OqC3NpEFgMIgB-4QBAC-Tk"

```
HTTP/1.1 404 Not Found
Alt-Svc: h3=":443"; ma=86400
Connection: keep-alive
Content-Encoding: gzip
Content-Type: application/json;charset=utf-8
Date: Sun, 01 Jun 2025 10:57:59 GMT
Server: openresty
Transfer-Encoding: chunked
Vary: accept-encoding, Origin
Via: 1.1 71cbe01df9e5102d886edc4f5a32c1ea.cloudfront.net (CloudFront)
X-Amz-Cf-Id: BBwudbiDTDnPQOgsUnLUw0nL3mLXQFzcLx2t8v09kc5ioA7sr2aEww==
X-Amz-Cf-Pop: LHR50-P2
X-Cache: Error from cloudfront
x-az: us-east-1b
x-task-id: 0091e8d404bb4c579424a9eabac49dd4

{
    "status_code": 34,
    "status_message": "The resource you requested could not be found.",
    "success": false
}
```

### [Rating A Movie](https://launchschool.com/books/working_with_apis/read/tmdb_api#ratingmovies)

- the documentation says we need:
  - a URL like this: `https://api.themoviedb.org/3/movie/{movie_id}/rating`
  - a value between 0.5 and 10
  - a POST method
  - our access token
- http POST https://api.themoviedb.org/3/movie/27205/rating \
    "Authorization: Bearer eyJhbGciOiJIUzI1NiJ9.eyJhdWQiOiIzMDY5ZjIyNjc4YmJkODliZDRhNmQyY2IwYzI0OWUzNCIsIm5iZiI6MTc0ODc3NDkzMC40NjQsInN1YiI6IjY4M2MzMDEyZTg2NTYzYjgxMWQyMTIxZSIsInNjb3BlcyI6WyJhcGlfcmVhZCJdLCJ2ZXJzaW9uIjoxfQ.5GIHNExqKPBkcsqbcE414OqC3NpEFgMIgB-4QBAC-Tk" \
    value:=9

```
HTTP/1.1 201 Created
Alt-Svc: h3=":443"; ma=86400
Connection: keep-alive
Content-Type: application/json;charset=utf-8
Date: Sun, 01 Jun 2025 11:00:40 GMT
Server: openresty
Transfer-Encoding: chunked
Via: 1.1 ce8f85a4dd9437febbc40094aa7d575a.cloudfront.net (CloudFront)
X-Amz-Cf-Id: zYb9Rh8on0FXajrCMfFzAOh8_4ZCeQeFqxb5vIl8_0gig0CQqr5JGw==
X-Amz-Cf-Pop: LHR50-P2
X-Cache: Miss from cloudfront
cache-control: public, max-age=0
content-encoding: gzip
etag: W/"4543905c5703940a323f39bb4fdcba82"
vary: accept-encoding, Origin
x-az: us-east-1c
x-task-id: 19248da2e9fe44b5bbd72d15bd3bc48f

{
    "status_code": 1,
    "status_message": "Success.",
    "success": true
}
```

- behind the scenes TMDB:
  - checks the movei exists
  - checks we haven't already rated this movie
  - recalculates the movie's average rating
  - records this rating in our account history

### [Deleting A Rating](https://launchschool.com/books/working_with_apis/read/tmdb_api#deletingrating)

- http DELETE https://api.themoviedb.org/3/movie/27205/rating \
    "Authorization: Bearer eyJhbGciOiJIUzI1NiJ9.eyJhdWQiOiIzMDY5ZjIyNjc4YmJkODliZDRhNmQyY2IwYzI0OWUzNCIsIm5iZiI6MTc0ODc3NDkzMC40NjQsInN1YiI6IjY4M2MzMDEyZTg2NTYzYjgxMWQyMTIxZSIsInNjb3BlcyI6WyJhcGlfcmVhZCJdLCJ2ZXJzaW9uIjoxfQ.5GIHNExqKPBkcsqbcE414OqC3NpEFgMIgB-4QBAC-Tk"

```
HTTP/1.1 200 OK
Alt-Svc: h3=":443"; ma=86400
Connection: keep-alive
Content-Type: application/json;charset=utf-8
Date: Sun, 01 Jun 2025 11:04:29 GMT
Server: openresty
Transfer-Encoding: chunked
Via: 1.1 0ed0b3a1a3e8908d48a47272b433d54e.cloudfront.net (CloudFront)
X-Amz-Cf-Id: YarYnZNVa2bKo6wERaBK0UwHtacyEbj7NXXXOB11qBkqVOAO7TwFgQ==
X-Amz-Cf-Pop: LHR50-P2
X-Cache: Miss from cloudfront
cache-control: public, max-age=0
content-encoding: gzip
etag: W/"0566f98871ddfd7f6ade28aaefb5167d"
vary: accept-encoding, Origin
x-az: us-east-1b
x-task-id: 8b4e2f6569074cd88a533175c64bc4e0

{
    "status_code": 13,
    "status_message": "The item/record was deleted successfully.",
    "success": true
}
```

### [TMDB API and REST Principles Analysis](https://launchschool.com/books/working_with_apis/read/tmdb_api#apirestanalysis)

##### Resource Design

- good, noun-based, so not 'getMovie' or 'createRadting', but `GET` and `POST`.

##### HTTP Methods

- Ideally we'd use `PUT` or `PATCH` for updates, rather than `POST` as they do. It's a trade-off: less RESTful, but devs don't have to check whether a rating exists before deciding whether to use post or put.

##### Error handling approach

- unconventional, but deliberate.

```
{
    "status_code": 7,
    "status_message": "Invalid API key: You must be granted a valid key.",
    "success": false
}
```
- they have their own custom status code system.
- Problems:
  - this custom code is not self-documenting, you have to search for what the code means.
  - The success field doesn't tell us anything new, the success is displayed in the HTTP status code.

##### Real-World Impact

- They made these choices for a reason.
- If they want to update the API now it has to be done very carefully, probably releasing a new version of the API, so users can opt-in or not to the changes.
- One must balance the potential disruption with the advantages of the update.

##### What we can learn

- even widely used APIs are imperfect
- Always read documentation carefully, don't assume this API will be like others.
- Check example responses in documentation.
- Even imperfect APIs can be useful

### Exercises:

This works:

http GET https://api.themoviedb.org/3/movie/27205 \
    "Authorization: Bearer eyJhbGciOiJIUzI1NiJ9.eyJhdWQiOiIzMDY5ZjIyNjc4YmJkODliZDRhNmQyY2IwYzI0OWUzNCIsIm5iZiI6MTc0ODc3NDkzMC40NjQsInN1YiI6IjY4M2MzMDEyZTg2NTYzYjgxMWQyMTIxZSIsInNjb3BlcyI6WyJhcGlfcmVhZCJdLCJ2ZXJzaW9uIjoxfQ.5GIHNExqKPBkcsqbcE414OqC3NpEFgMIgB-4QBAC-Tk"


1.

http GET "https://api.themoviedb.org/3/search/movie?query=Lilo%20and%20Stitch" \
  "Authorization: Bearer eyJhbGciOiJIUzI1NiJ9.eyJhdWQiOiIzMDY5ZjIyNjc4YmJkODliZDRhNmQyY2IwYzI0OWUzNCIsIm5iZiI6MTc0ODc3NDkzMC40NjQsInN1YiI6IjY4M2MzMDEyZTg2NTYzYjgxMWQyMTIxZSIsInNjb3BlcyI6WyJhcGlfcmVhZCJdLCJ2ZXJzaW9uIjoxfQ.5GIHNExqKPBkcsqbcE414OqC3NpEFgMIgB-4QBAC-Tk"

http GET "https://api.themoviedb.org/3/search/movie?query=Sikandar" \
  "Authorization: Bearer eyJhbGciOiJIUzI1NiJ9.eyJhdWQiOiIzMDY5ZjIyNjc4YmJkODliZDRhNmQyY2IwYzI0OWUzNCIsIm5iZiI6MTc0ODc3NDkzMC40NjQsInN1YiI6IjY4M2MzMDEyZTg2NTYzYjgxMWQyMTIxZSIsInNjb3BlcyI6WyJhcGlfcmVhZCJdLCJ2ZXJzaW9uIjoxfQ.5GIHNExqKPBkcsqbcE414OqC3NpEFgMIgB-4QBAC-Tk"

http GET "https://api.themoviedb.org/3/search/movie?query=Fountain%20of%20Youth" \
  "Authorization: Bearer eyJhbGciOiJIUzI1NiJ9.eyJhdWQiOiIzMDY5ZjIyNjc4YmJkODliZDRhNmQyY2IwYzI0OWUzNCIsIm5iZiI6MTc0ODc3NDkzMC40NjQsInN1YiI6IjY4M2MzMDEyZTg2NTYzYjgxMWQyMTIxZSIsInNjb3BlcyI6WyJhcGlfcmVhZCJdLCJ2ZXJzaW9uIjoxfQ.5GIHNExqKPBkcsqbcE414OqC3NpEFgMIgB-4QBAC-Tk"

2.

Movie 1: Lilo & Stitch:

http POST "https://api.themoviedb.org/3/account/22048510/watchlist \
     --header 'Authorization: Bearer eyJhbGciOiJIUzI1NiJ9.eyJhdWQiOiIzMDY5ZjIyNjc4YmJkODliZDRhNmQyY2IwYzI0OWUzNCIsIm5iZiI6MTc0ODc3NDkzMC40NjQsInN1YiI6IjY4M2MzMDEyZTg2NTYzYjgxMWQyMTIxZSIsInNjb3BlcyI6WyJhcGlfcmVhZCJdLCJ2ZXJzaW9uIjoxfQ.5GIHNExqKPBkcsqbcE414OqC3NpEFgMIgB-4QBAC-Tk' \
     --header 'accept: application/json' \
     --header 'content-type: application/json'

GET https://api.themoviedb.org/3/account?api_key=eyJhbGciOiJIUzI1NiJ9.eyJhdWQiOiIzMDY5ZjIyNjc4YmJkODliZDRhNmQyY2IwYzI0OWUzNCIsIm5iZiI6MTc0ODc3NDkzMC40NjQsInN1YiI6IjY4M2MzMDEyZTg2NTYzYjgxMWQyMTIxZSIsInNjb3BlcyI6WyJhcGlfcmVhZCJdLCJ2ZXJzaW9uIjoxfQ.5GIHNExqKPBkcsqbcE414OqC3NpEFgMIgB-4QBAC-Tk&session_id=YOUR_SESSION_ID

curl -X GET "https://api.themoviedb.org/3/authentication/token/new?api_key=3069f22678bbd89bd4a6d2cb0c249e34"

https://www.themoviedb.org/authenticate/fdd4452cf6eec5d78e81a9bc286fc2e9e144df59

curl -X POST "https://api.themoviedb.org/3/authentication/session/new?api_key=3069f22678bbd89bd4a6d2cb0c249e34" \
  -H "Content-Type: application/json" \
  -d '{"request_token":"fdd4452cf6eec5d78e81a9bc286fc2e9e144df59"}'
  - returns `{"success":true,"session_id":"e7998e4d72f207a042376f958ff12ae43b47f6c0"}`

GET https://api.themoviedb.org/3/account?api_key=3069f22678bbd89bd4a6d2cb0c249e34&session_id=e7998e4d72f207a042376f958ff12ae43b47f6c0

```
hello there: HTTP/1.1 401 Unauthorized
Alt-Svc: h3=":443"; ma=86400
Connection: keep-alive
Content-Encoding: gzip
Content-Type: application/json;charset=utf-8
Date: Sun, 01 Jun 2025 11:50:13 GMT
Server: openresty
Transfer-Encoding: chunked
Vary: accept-encoding, Origin
Via: 1.1 0ed0b3a1a3e8908d48a47272b433d54e.cloudfront.net (CloudFront)
X-Amz-Cf-Id: L_lMtaKpYYOOkXfuj3ILpdZQmprbdr98Uggv0QafCgP_XjWwp3fR1w==
X-Amz-Cf-Pop: LHR50-P2
X-Cache: Error from cloudfront
x-az: us-east-1b
x-task-id: c48e0a81c0964062b5f95e61bfbac73e

{
    "status_code": 3,
    "status_message": "Authentication failed: You do not have permissions to access the service.",
    "success": false
}
```
- fuck

- get the movie ID:
http GET "https://api.themoviedb.org/3/search/movie?query=Lilo%20and%20Stitch" \
  "Authorization: Bearer eyJhbGciOiJIUzI1NiJ9.eyJhdWQiOiIzMDY5ZjIyNjc4YmJkODliZDRhNmQyY2IwYzI0OWUzNCIsIm5iZiI6MTc0ODc3NDkzMC40NjQsInN1YiI6IjY4M2MzMDEyZTg2NTYzYjgxMWQyMTIxZSIsInNjb3BlcyI6WyJhcGlfcmVhZCJdLCJ2ZXJzaW9uIjoxfQ.5GIHNExqKPBkcsqbcE414OqC3NpEFgMIgB-4QBAC-Tk"
  > 552524
- Get your account Id:
  - curl "https://api.themoviedb.org/3/account?api_key=3069f22678bbd89bd4a6d2cb0c249e34&session_id=e7998e4d72f207a042376f958ff12ae43b47f6c0"
    - {"avatar":{"gravatar":{"hash":"b0c996a676932046ee8f310136e1c878"},"tmdb":{"avatar_path":null}},"id":22048510,"iso_639_1":"en","iso_3166_1":"GB","name":"","include_adult":false,"username":"sandyPunandi"}
    - "id":22048510
- send a post:
  - curl -X POST "https://api.themoviedb.org/3/account/22048510/watchlist?api_key=3069f22678bbd89bd4a6d2cb0c249e34&session_id=e7998e4d72f207a042376f958ff12ae43b47f6c0" \
  -H "Content-Type: application/json" \
  -d '{"media_type": "movie", "media_id": 11544, "watchlist": true}'
    - response: `{"success":true,"status_code":1,"status_message":"Success."}`

Movie 2: Sikandar

- get the movie ID:
http GET "https://api.themoviedb.org/3/search/movie?query=Sikandar" \
  "Authorization: Bearer eyJhbGciOiJIUzI1NiJ9.eyJhdWQiOiIzMDY5ZjIyNjc4YmJkODliZDRhNmQyY2IwYzI0OWUzNCIsIm5iZiI6MTc0ODc3NDkzMC40NjQsInN1YiI6IjY4M2MzMDEyZTg2NTYzYjgxMWQyMTIxZSIsInNjb3BlcyI6WyJhcGlfcmVhZCJdLCJ2ZXJzaW9uIjoxfQ.5GIHNExqKPBkcsqbcE414OqC3NpEFgMIgB-4QBAC-Tk"
  > 1257960
- POST with HTTPie this time:

http POST "https://api.themoviedb.org/3/account/22048510/watchlist" \
  api_key==3069f22678bbd89bd4a6d2cb0c249e34 \
  session_id==e7998e4d72f207a042376f958ff12ae43b47f6c0 \
  Content-Type:application/json \
  media_type=movie media_id:=1257960 watchlist:=true

Movie 3: Fountain of Youth

id = 1098006

http POST "https://api.themoviedb.org/3/account/22048510/watchlist" \
  api_key==3069f22678bbd89bd4a6d2cb0c249e34 \
  session_id==e7998e4d72f207a042376f958ff12ae43b47f6c0 \
  Content-Type:application/json \
  media_type=movie media_id:=1098006 watchlist:=true
  
## REFERENCE
## [HTTP Response Headers](https://launchschool.com/books/working_with_apis/read/http_response_headers)
 
 - This page is a list of the most common HTTP response headers:

### [Access-Control-Allow-Origin](https://launchschool.com/books/working_with_apis/read/http_response_headers#accesscontrolalloworigin)

- gives a list of what domains can access this resource using CORS.
- THis would allow all sites: `Access-Control-Allow-Origin: *`

### [Allow](https://launchschool.com/books/working_with_apis/read/http_response_headers#allow)

- lists what methods are allowed

### [Content-Length](https://launchschool.com/books/working_with_apis/read/http_response_headers#contentlength)

- length of the response body in bytes

### [Content-type](https://launchschool.com/books/working_with_apis/read/http_response_headers#contenttype)

describes the media-type or format of the body

### [ETag](https://launchschool.com/books/working_with_apis/read/http_response_headers#etag)

- used to specify a version of a resource

### [Last-Modified](https://launchschool.com/books/working_with_apis/read/http_response_headers#lastmodified)

The last time the request was modified.

### [WWW-Authenticate](https://launchschool.com/books/working_with_apis/read/http_response_headers#wwwauthenticate)

- what type of authentication is required to access a resource

### [X-* Headers](https://launchschool.com/books/working_with_apis/read/http_response_headers#xheader)

-lists headers beginning with x. If they begin with x it means they're not standardized headers, often API specific.
