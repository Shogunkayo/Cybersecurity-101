
# URL 
- Uniform Resource Locator

![[newurl.png]]


- Scheme -> what protocol to use 
- User -> username and password of person logged in 
- Host -> domain name or ip address of the server
- Port -> port to connect, can be hosted on any port between 1-65535, usually 80 - HTTP, 443 - HTTPS
- Path -> filename or location of resource
- Query String -> extra info that can be sent to the requested path
- Fragment -> reference to a location on the actual page requested 

### Making a request
GET / HTTP/1.1

- for better experience, other data needs to be sent in headers 

GET /HTTP/1.1
Host: tryhackme.com
User-Agent: Mozilla/5.0 Firefox/87.0
Referer: https://tryhackme.com/


- HTTP requests always end with a blank line to inform the web server that the request is completed

![[httpresponse.PNG]]


# METHODS
----
- ways for a client to show their intended actions

### GET 
- Used for getting information from a web server

### POST
- submitting data to the web server and creating new records

### PUT
- submitting data to the web server to update information

### DELETE
- deleting informtaion/records from a web server


# STATUS CODES
---
![[status-codes-1.PNG]]![[status-codes-2.PNG]]


# HEADERS
----
- Host -> some web servers host multiple websites, 