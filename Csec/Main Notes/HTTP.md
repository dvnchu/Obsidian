[[web]]

HyperText Transfer Protocol

the set of rules used for communicating with web servers for the transmitting of webpage data.

## HTTPS 
(HyperText Transfer Protocol Secure)
Is the secure version of HTTP. HTTPS data is encrypted so it not only stops people from seeing the data you are receiving and sending, but it also gives you assurances that it is the correct web 


## Request

````http
GET / HTTP/1.1

Host: tryhackme.com
User-Agent: Mozilla/5.0 Firefox/87.0
Referer: https://tryhackme.com/
````

+ Line 1: This request is sending the GET method, request the home page with / and telling the web server we are using HTTP version 1.1

+ Line 2: We tell the server the website

+ Line 3: we tell the browser and the version

+ Line 4: we are telling the web server that this is the web page that referred us to this one.

+ Line 5: HTTP request always end with a blank line
## Response

````http
HTTP/1.1 200 OK

Server: nginx/1.15.8
Date: Fri, 09 Apr 2021 13:34:03 GMT
Content-Type: text/html
Content-Length: 98


<html>
<head>
    <title>TryHackMe</title>
</head>
<body>
    Welcome To TryHackMe.com
</body>
</html>
````

+ Line 1: The version and the status code "200 OK" which tells us the request has completed successfully

+ Line 2: this tells us the web server software and version

+ Line 3: The current date, time and timezone of the server

- Line 4: The content-type header

- Line 5: How long the response is

- Line 6: blank line

+ Line 7-14: the info requested

## Methods

### Get Request
Gets information from a web server.
### Post Request
Used for submitting data to the web server and potentially creating new records
### Put Request
This is used for submitting data to a web server to update info
### Delete Request
This is used for deleting info/records from a server


## Status Codes

|                                    |                                                                                                                                                                                        |
| ---------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **100-199 - Information Response** | These are sent to tell the client the first part of their request has been accepted and they should continue sending the rest of their request. These codes are no longer very common. |
| **200-299 - Success**              | This range of status codes is used to tell the client their request was successful.                                                                                                    |
| **300-399 - Redirection**          | These are used to redirect the client's request to another resource. This can be either to a different webpage or a different website altogether.                                      |
| **400-499 - Client Errors**        | Used to inform the client that there was an error with their request.                                                                                                                  |
| **500-599 - Server Errors**        | This is reserved for errors happening on the server-side and usually indicate quite a major problem with the server handling the request.                                              |

### Common status Codes

|   |   |
|---|---|
|**200 - OK**|The request was completed successfully.|
|**201 - Created**|A resource has been created (for example a new user or new blog post).|
|**301 - Moved Permanently**|This redirects the client's browser to a new webpage or tells search engines that the page has moved somewhere else and to look there instead.|
|**302 - Found**|Similar to the above permanent redirect, but as the name suggests, this is only a temporary change and it may change again in the near future.|
|**400 - Bad Request**|This tells the browser that something was either wrong or missing in their request. This could sometimes be used if the web server resource that is being requested expected a certain parameter that the client didn't send.|
|**401 - Not Authorised**|You are not currently allowed to view this resource until you have authorised with the web application, most commonly with a username and password.|
|**403 - Forbidden**|You do not have permission to view this resource whether you are logged in or not.|
|**405 - Method Not Allowed**|The resource does not allow this method request, for example, you send a GET request to the resource /create-account when it was expecting a POST request instead.|
|**404 - Page Not Found**|The page/resource you requested does not exist.|
|**500 - Internal Service Error**|The server has encountered some kind of error with your request that it doesn't know how to handle properly.|
|**503 - Service Unavailable**|This server cannot handle your request as it's either overloaded or down for maintenance.|

## Headers
Not strictly required when making a request, but you'll find it difficult to view a website without them

### Common Headers

#### Request
##### Host
Some web servers host multiple websites with this one you can tell which one you require.
##### User-Agent
Browser software and version number, helps to format and if elements of HTML, JS, and CSS are available.
##### Content-Length
Tells the server how much data to expect.
##### Accept Encoding
Types of compression methods that the browser supports so the data can be made smaller for transmitting.
##### Cookie
Data sent to the server to help remember your info

#### Response
##### Set-Cookie
Info to store which gets sent back to the server on each request
##### Cache-control
How long to store the content of the response in the browser's cache before it requests it again.
##### Content-Type
Tells the client what type of data is being returned.
##### Content-Encoding 
What method has been used to compress the data sending it over the internet.

## Cookies 
they're just a small piece of data that is stored on your computer.
Cookies are saved when you receive a "Set-Cookie" Header from a web server. Then every further request you make, you'll send the cookie data back to the web server.
Because HTTP is stateless (doesn't keep track of your previous requests), cookies can be used to remind the web server who you are, personal setting, or if you've been on the website before.

![[Pasted image 20251219170839.png]]

Cookies can be used for many purposes but are most commonly used for website authentication. The cookie value won't usually be a clear-text string where you can see the password, but a token (unique secret code that isn't easily humanly guessable).
