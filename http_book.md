# [Http Book](https://launchschool.com/books/http)
# [Background](https://launchschool.com/books/http/read/background)

## [Introduction](https://launchschool.com/books/http/read/introduction#gettingstarted)
- Your browser is the interface/window through which you interact with the World Wide Web.
- Under you browser's hood lies a collection of files that make viewing the page possible:
  - CSS
  - HTML
  - Javascript
  - Videos
  - Images
- All these files were sent from a **server** to your browser (the **client**) by an application protocol called **HTTP**. (which is why URLs in your browser search bar start with 'http://'.
- HyperText Transfer Protocol acts as a link between applications and transfers hypertext documents.
- HTTP follows a simple model:
  - A client makes a request to a server and waits for a response. (**request response protocol**). These request and response messages are like text messages or strings, which are formatted in a language the other machine understands.

HTTP has been through several changes since its inception:

|Date  | version| Description | 
| :--- | :---: | :---: | 
|At the start|HTTP protocol|Only transmits HTML pages
|1991|HTTP/0.9| Can transmit Documents
|1992|HTTP/1.0| Can transmit CSS documents, videos, scripts, images
|1995|HTTP/1.1|Can re-use established connections for subsequent requests|
|1999|still HTTP/1.1| Mostly as we use it today
|?|HTTP/2|is fast gaining traction|
|?|HTTP/3|currently in development|

### How the internet works

- The internet is made of millions of networks composed of many kinds of computers which all communicate with each other.
- By convention all computers that make up a network are assigned an IP address.
- An Internet Protocol Number is like a phone number for that computer.
- Port numbers add more detail about how to talk to that computer (like a phone extention).
- An IP address might look like this: `192.168.0.1`
- With a port number added it would look like this: `192.168.0.1:1234`
- An IP address acts as the identifier for a device or server. Within that there could be hundreds or thousands of ports.
- With the wider internet communication occurs when each device has a public IP address provided by an **internet service provider**.
- If we need an IP address to get anywhere, why do website addresses look like 'www.google.com' ? 

### DNS

- Domain Name System: This maps the address to the IP address.
- DNS is a distributed database that translates the names we humans use to IP addresses so that they can be sent to a server.
- It still works to type an IP address directly into the address bar.
- DNS databases are stored on computers called DNS servers.
- There is a huge global hierarchical network of DNS servers. No single one contains the whole database.
- If a DNS server does not contain the address it passes the request up the chain to the next DNS server. Eventually the address will be found in a DNS database and the coresponding IP address will be used to receive the request.
- A typical interaction with the internet could look like this:
  - type a URL into the address bar
  - The browser creates a HTTP request, which is packaged up and sent to your device's network interface.
  - If your device already has a record of the IP address for the domain name in its DNS cache it will use that. If not, a request will be made to the Domain Name System to obtain it.
  - The packaged up HTTP request then goes over the internet where it is directed to the server with the matching IP address.
  - The remote server accepts the request and sends a response over the internet back to your network interface which hands it to your browser.
  - The browser displays this response as a web-page.
- Your browser issueing a request is simply sending some text to an IP address.
- The client (web-browser) and server (recipient of the request) have an agreed protocol (HTTP) which allows the server to:
  -  take apart the request
  -  Understand each component
  -  Send a response back to the web-browser.
-  The web browser then translates this response into a form you can understand.
-  All websites use HTTP. Even though you are unaware of it. Your browser is sending requests and processing the responses automatically.

 <p align="center">
<img width="709" alt="Screenshot 2023-04-12 at 23 25 31" src="https://user-images.githubusercontent.com/78854926/231599537-cda34f97-5685-434d-b900-9d3916224952.png">
 </p>
 
### [Clients and Servers](https://launchschool.com/books/http/read/background#clientsandserver)

- The most common client is an application called a web browser (ie Internet Explorer, Firefox, Chome, Safari, including mobile versions)
- Their job is to send the HTTP request and process the HTTP response in a user friendly manner. 
- Web-browsers aren't the only clients around. There are other ways and applications that can issue HTTP requests.
- The content you request is on a server, which is a remote-computer.
- Servers are machines that can handle inbound requests and issue a response back. Often the response contains data specified in the request. 

<p align="center">
<img width="608" alt="Screenshot 2023-04-12 at 23 37 34" src="https://user-images.githubusercontent.com/78854926/231601325-5dec5165-9e08-4520-864e-b47bd6d51491.png">
</p>

### [Resources](https://launchschool.com/books/http/read/background#resources)

- 'Resource' is a generic term for things on the internet which you can interact with via a URL. Images, videos, web-pages, other files or even stock-trading software and video-game software. There's a lot of them about.

<p align="center">
<img width="640" alt="Screenshot 2023-04-12 at 23 40 33" src="https://user-images.githubusercontent.com/78854926/231601830-b8beec9d-6579-4852-93d0-5b9490ad78d3.png">
</p>

### [Statelessness](https://launchschool.com/books/http/read/background#statelessness)

- A protocol is said to be stateless when each request/response pair is completely independent of the previous one.
- HTTP is a stateless protocol and this has implications for server resources and ease of use.
- It means that the server does not need to hang on to information or state between requests.
- This means that when a request breaks on route to the server no part of the system has to do any clean-up.
- This makes HTTP a risilient protocol. It also makes it a difficult protocol for building stateful applications.
- Since HTTP is inhernetly stateless, that means web developers need to work hard to create stateful experiences in web-applications.
- A example of this is remaining logged into something, while completing more request/response cycles. And how does the website even know these requests are coming from you?
- There are tricks that make it seem like an experience is stateful, but those tricks are not covered in this book.
- Just remember, even though you think an experience is stateful, the web is built of HTTP, which is stateless.

|pros of statelessness  | cons of statelessness 
| :--- | :---: | 
|resilient|difficult to secure
|distributed|difficult to build on top op
|hard-to-control|

## [What is a URL?](https://launchschool.com/books/http/read/what_is_a_url)

### [Introduction](https://launchschool.com/books/http/read/what_is_a_url#introduction)

- It's the technical name for the website address.
- It's a type of URI (Uniform Resource Identifier), but not the only kind. URIs specify how resources are located.

### [URL components](https://launchschool.com/books/http/read/what_is_a_url#urlcomponents)

http://www.example.com:88/home?item=book

|section  |name |function
| :--- | :---: |  :---: | 
|http| The **scheme** | Always comes before the colon and two slashes. This tells the web-client how to access the resource. In this case it says to use HyperText Transfer Protocol. (other popular URL schemes are `ftp`, `mailto`, or `git`. It's sometimes called the protocol, but it is more correct to say scheme.  The scheme can indicate which protocol to use, but they're not the same thing.
|www.example.com|The **host**| Tells the client where the resource is hosted|
|:88|The port number| Only required if you want to use a port which is not the default.
|/home|The path| Shows what local resource is being requested. This part of the URL is optional
|?item=book|The **query string** made of **query parameters**| To send data to the server (also optional)

<p align="center">
<img width="593" alt="Screenshot 2023-04-13 at 00 12 47" src="https://user-images.githubusercontent.com/78854926/231605929-8b9d9ceb-3bfb-438b-8dfc-52bd53e53ace.png">
</p>

- Sometimes the path can point to a specific resource on the host. ie. http://www.example.com/home/index.html
- The default port for HTML is 80. A non-default port could look like this:http://localhost:3000/profile

### [Query Strings and parameters](https://launchschool.com/books/http/read/what_is_a_url#querystringsparameters)

- A simple url with a query string could look like this:

`http://www.example.com?search=ruby&results=10`

|Query string component  |Description
| :--- | :---: |  
|?|This is a reserved character that marks the start of a query string
|search=ruby|This is a parameter name/value pair
|&| This is a reserved character used when adding more parameters to the query string
|results=10| This is also a parameter name value pair

For example:

```
http://www.phoneshop.com?product=iphone&size=32gb&color=white
```

<p align="center">
<img width="682" alt="Screenshot 2023-04-13 at 08 33 04" src="https://user-images.githubusercontent.com/78854926/231687023-1dbc9695-f7ff-429e-b9e8-34f104108580.png">
</p>

- Here 3 name value pairs are passed to the server from the URL:
  - `product=iphone`
  - 'size=32gb'
  - 'color-white'
- This is asking the `phoneshop` server to narrow down on a product, `iphone`, size '32gb' and colour 'white'. What the server doe with these parameters is up to the server side application.
- **Because query strings are passed in from the URL they are only used in HTTP GET requests.**
- There are different types of HTTP requests. Typing a URL into the browser is a HTTP GET request. Most links do too.

<p align="center">
<img width="689" alt="Screenshot 2023-04-13 at 08 42 23" src="https://user-images.githubusercontent.com/78854926/231689211-322e15cf-ccb0-4af7-92d3-5069b1026ff2.png">
</p>

- Query strings are great for passing additional information to the server, but here are some disadvantages:
  - Max length: If you have a lot of data to pass you won't be able to do it with query strings.
  - Name/Value pairs are visible in the URL. So passing things like passwords is ill-advised.
  - Space and special characters like `&` can't be used with query strings they must be URL 

### [URL encoding](https://launchschool.com/books/http/read/what_is_a_url#urlencoding)

- URLs can only accept certain ASCII characters.
- Chars which have to be encoded:
  - reserved chars
  - unsafe chars
  - chars not from 128 character ASCII set.
- URL encoding replaces these chars with `%` and a hexadecimal number representing the equivalent UTF-8 number.
- You don't need to get UTF-8, just know that it uses 1-4 bytes to represent every possible character in the Unicode character set.
- Here are some popular encoded characters and examples:

|Char  |UTF-8 code|URL
| :--- | :---: | :---: |
|space|%20|http://www.thedesignshop.com/shops/tommy%20hilfiger.html
|$|%24|http://www.spam.com/i-have-%2410-million-for-you
|£|%C2%A3| http://www.spam.com/big-inheritance-%C2%A3-millions
|€|%E2%82%AC|http://www.spam.com/big-inheritance-%E2%82%AC-millions
|𐍈|%F0%90%8D%88|http://www.symbols-of-the-world.com/hwair-%F0%90%8D%88

- All characters in the ASCII set have equivalent UTF-8 numbers. 
- Characters must be encoded if:
  - They have no coresponding character within the standard ASCII character set.
  - Using characters would be unsafe because it could be modified or misinterpreted by some systems. For example `%` is unsafe because it is used to encode other characters. Other unsafe characters include (but are not limited to):
    - spaces
    - "
    - #
    - >
    - <
    - {
    - }
    - [
    - ]
    - ~
  - The character is reserved for special use in the URL. For example:
    -  ?
    -  : (delimits host/port components and user/password.
    -  @
    -  & (is a query string delimiter)

- What characters can be used safely within a URL?
  - Alphanumeric characters
  - _
  - .
  - +
  - !
  - '
  - (
  - )
  - ' (this is clarified [here](https://launchschool.com/posts/915605ee) which explains that single quote are safe but double quotes are unsafe)
  - , 
  - Reserved characters when used for their reserved purpose.

### [Summary](https://launchschool.com/books/http/read/what_is_a_url#summary)

# HTTP

## [Preparations](https://launchschool.com/books/http/read/preparations)

### [HTTP GUI tools](https://launchschool.com/books/http/read/preparations#httpguitools)

-  I chose paw (or [RapidAPI](https://paw.cloud)) 

### [HTTP command line tools](https://launchschool.com/books/http/read/preparations#httpcommandlinetools)

- Curl is available with the command `curl www.google.com`

## [Making Requests](https://launchschool.com/books/http/read/making_requests)

### [HTTP request with a browser](https://launchschool.com/books/http/read/making_requests#httprequestwithabrowser)

- Example of typing in https://www.reddit.com
- The server that hosts the main Reddit website handles your request and sends back a response to your browser. Your browser renders that as the website you see.

### [HTTP request with an HTTP tool](https://launchschool.com/books/http/read/making_requests#httprequestwithhttptool)

- How do we see the raw HTTP data? We use an HTTP tool
- It issues the request and displays the raw text data.
- For a trainee web-developer you need to be able to scan and understand this raw data. Just to get a general idea.

### [Using the inspector](https://launchschool.com/books/http/read/making_requests#usingtheinspector)

- Every modern browser has a way to view HTTP requests, usually called an inspector.
- `option + command + i` to pop it up.
- Just by entering a URL your browser is making multiple requests. One for every resource.
- The initial request for `www.website.com` returns an HTML file containing references to many other resources. Your browser understands that these resources need to be found and issues requests for them.
- You can see all of these sub-requests (my term) in the inspector tool. 
- `curl` is less decipherable.
- Bear in mind that Reddit now requires a User-Agent to be added to any HTTP request to prevent bots from accessing the site. That looks like this:

``` 
-A 'User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10_9_5) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/38.0.2125.101 Safari/537.36'
```
### [Request Methods](https://launchschool.com/books/http/read/making_requests#requestmethods)

- Looking at the 'Method' and 'status' columns.
- In the Method column you have HTTP Request Methods. This is like a verb that tells teh server what actioins to perform in a resource.
- The two most common commands are `GET` and `POST`.
- The status column shows response status for each request.
- Every request gets a response, even if it is `ERROR`.(... unless they timeout, but that's rare).

### [Get Requests](https://launchschool.com/books/http/read/making_requests#get)

- Initiated by clicking a link or putting an address in the browser bar.
- The default behaviour of a link is to issue a `GET` request to a URL.
- To remember for now:
  - GET requests are used to retrieve a resource. Most links are GET requests
  - The response to a GET request can be anything, but if it is HTML and that HTML references other resources then your browser will automatically issue GET requests for those. (A pure HTML tool will not).

### [Post requests](https://launchschool.com/books/http/read/making_requests#post)

- To send/submit data or initiate an action to/on the server.
- POST requests allow us to send much larger and sensitive data to the server, like images and videos. 
- This is because the alternative is sending a GET request with the information written in the query string, which would be:
  - Exposing our credentials.
  - Limited in size
-  I'm receiving a 303 response, i'm not sure if that's a bad thing. But what I'm supposed to be demonstrating is that the data is being submitted to the server, not via the URL but in the HTTP body. The body contains the data that is being transmitted in a HTML message. So and HTTP message can be sent with an empty body.
  - Or the body can contain HTML messages, images, videos. The body is like the letter inside an envelope.
  - Filling out the POST request is (meant to be) the same as you filling out the form on the web-page itself.
  - The HTTP response to our POST is `Location: http://al-blackjack.herokuapp.com/bet` which shows the webpage we are directed to once we've filled out the name form.
  - The `location` header is a response header (because responses have headers too). More on headers later.
  - Your browser sees 'Location' in the header and automatically issues the next request for the URL specified. SO the "make a bet" page is the response to that second request.
  - Remember : when using a browser most of the request/response cycles are hidden from you.

### [HTTP Headers](https://launchschool.com/books/http/read/making_requests#httpheaders)

- HTTP headers allow the client and server to send additional information during the HTTP request/response cycle.
  - Headers are colon-seperated name-value pairs that are sent in plain text.
  - we can look at them in raw form in the Inspector. (mine doesn't look like this?)

<p align="center">
<img width="700" alt="Screenshot 2023-04-13 at 13 08 18" src="https://user-images.githubusercontent.com/78854926/231753681-b3f21d5d-99b4-4da4-8604-3fdf20589c93.png">
</p>

- Here are the various headers being sent during a request/response cycle.
## Processing responses
## Stateful Web Applications
## Security
## Conclusions and next steps

Overview:

|  | Once | Twice | Thrice | Comprehension | Retention
| :--- | :---: | :---: | :---: | :--- | :---
|1. Introduction| 12th April|
|2. Background| 12th April|
|3.  What is a URL?|13th April|
|4. Preparations|13th April|
|**HTTP**|
|5. Making requests|13th April|
|6.  Processing responses|
|7. Stateful web applications|
|8. Security|
|9. Conclusions and next steps|
