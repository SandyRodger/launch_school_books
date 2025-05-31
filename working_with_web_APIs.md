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

### XML

- Extensible Markup language
## REST and CRUD
## WORKING WITH AN API
## Fetching Resources
## Requests in Depth
## Creating Resources
## More HTTP Methods
## REAL WORLD APIS
## TMDB API
## REFERENCE
## HTTP Response Headers
