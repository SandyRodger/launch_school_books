# [Http Book](https://launchschool.com/books/http)

## [Introduction](https://launchschool.com/books/http/read/introduction#gettingstarted)
## [Background](https://launchschool.com/books/http/read/background)

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
  - a client makes a request to a server and waits for a response. (**request response protocol**). These request and response messages are like text messages or strings, which are formatted in a language the other machine understands.

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

## Preparations
## Making Requests
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
|4. Preparations|
|**HTTP**|
|5. Making requests|
|6.  Processing responses|
|7. Stateful web applications|
|8. Security|
|9. Conclusions and next steps|
