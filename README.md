## HTTP Questions

__URLs__

* Name all of the parts of the url that you can remember.  In your own words describe what they do.

```
protocol - usually HTTP/1.1
domain - the DNS name or IP
path - where on the server
querystring - additional parameters describing what is requested
port - used in combination with domain, different service use different standard ports, HTTP - 80, HTTPS - 443 ...
anchor - specifies a particular location on a page
```

* Name the pieces of the following urls:
	* `https://www.google.com/`
  protocol, domain, path (root)

	* `https://workbook.galvanize.com/cohorts/41/learning_experiences/367`
  protocol, domain, path 

	* `http://locahost:5000/animals/puppies?onlycute=1&size=medium#firstpuppy`
  protocol, domain, port, path, querystring anchor

	* `https://en.wikipedia.org/wiki/List_of_HTTP_status_codes#4xx_Client_Error`
  protocol, domain, path, anchor

* Can a server use more than 1 port?

```
Yes
```

* Why is https different than http?

```
encrypts data that is sent
```

* How does a server interpret the following url's query paramter.  What data structure does it create on the server?

```
http://locahost:5000/animals?puppies=fido&puppies=max&puppies=moxie
```
creates a JSON object that holds puppies and their names
__HTTP Request/Response__

* Name at least 4 http verbs

```
GET / POST / PUT / DELETE
```

* What is each verb useful for in your own words

```
GET client request to the server / POST sending (new) data onto the server / PUT changing exisitng data on the server/ DELETE removing data from the server
```

* What does idempotent mean?

```
Means to not affect the current state, in this case, of a server.
```

* Name the 5 http status code ranges.  What are they used for in general?

```
100 - in progress
200 - indicates success
300 - redirection
400 - failed request by client
500 - failed response on server side
```

* If a server returns a http status code of 301 and a location of `https://www.google.com/`, what does the browser do?

```
it redirects the client request to https://www.google.com/
```

* For the following HTTP headers, decide if the following header is used for requests, responses or both:
	* Accept
  request
	* Content-type
  both
	* User-agent
  request
	* Set-cookies
  response
	* Cache-control
  both
	* Cookie
  both

  
* Is the following a http request or response?  How do you know for each?

```
HTTP/1.1 200 OK
Access-Control-Allow-Origin: *
Vary: Accept
Content-Type: text/html; charset=utf-8
Content-Length: 722
ETag: W/"2d2-Wu0We9N5g35FXWY+gOATLA"
Date: Tue, 08 Mar 2016 20:37:11 GMT
Connection: keep-alive

<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <link rel="stylesheet" href="/style.css">
    <title>Student Roster</title>
  </head>
  <body>
    <main>
      <h1>Student Roster</h1>
      
        <section>
          <h3>Daenerys Targaryen</h3>
          <span>Student Id: nys8fbohl</span>
          <h4>Hobby: Motherhood</h4>
          <img src="https://i.imgur.com/KlycRG5.jpg" alt="Daenerys Targaryen" />
        </section>
      
        <section>
          <h3>Tyrion Lannister</h3>
          <span>Student Id: njehukbohe</span>
          <h4>Hobby: Traveling</h4>
          <img src="https://i.imgur.com/fFMusdC.png" alt="Tyrion Lannister" />
        </section>
      
    </main>
  </body>
</html>

--> this prior set is a server response, contains server status code 200. Also, holds page in the Body. 
```

```
DELETE /students/n1vmyrw3x HTTP/1.1
Host: g22-students.herokuapp.com
Accept: application/json
Cache-Control: no-cache
Postman-Token: 0041e3c3-efdb-f0c3-b2f4-2d79f6d0f44b

--> This us a request, using the Request VERB DELETE.
```


__JSON__

* Describe what JSON is.  What is it used for.

```
It's the format the server uses to parse data.
```

* Convert the following map into a javascript object then console log the age.

```
{ "company" : "Github", "age": 7, "categories" : "Services,Internet,Software"}

// answer
console.log(JSON.parse('{ "company" : "Github", "age": 7, "categories" : "Services,Internet,Software"}'));

```

* Convert the following to a javascript object.  Console log each company name.

```
{ "Companies":[ { "company": "Github", "age": 7, "categories": "Services,Internet,Software"},
              { "company": "Airbnb", "age": 6, "categories": "Hotels,Travel"},
              { "company": "Square", "age": 7, "categories": "FinTech,Hardware + Software,Finance"},
              { "company": "Dropbox", "age": 11, "categories": "Cloud Data Services,Storage,Web Hosting"}
            ]
}

// answer

JSON.stringify({ "Companies":[ { "company": "Github", "age": 7, "categories": "Services,Internet,Software"},
              { "company": "Airbnb", "age": 6, "categories": "Hotels,Travel"},
              { "company": "Square", "age": 7, "categories": "FinTech,Hardware + Software,Finance"},
              { "company": "Dropbox", "age": 11, "categories": "Cloud Data Services,Storage,Web Hosting"}
            ]
});

myJSONObj = JSON.parse('{"Companies":[{"company":"Github","age":7,"categories":"Services,Internet,Software"},{"company":"Airbnb","age":6,"categories":"Hotels,Travel"},{"company":"Square","age":7,"categories":"FinTech,Hardware + Software,Finance"},{"company":"Dropbox","age":11,"categories":"Cloud Data Services,Storage,Web Hosting"}]}');

myJSONObj.Companies.map(function(el){
return el.company
});

```

* The following is javascript.  Convert the object to a string and console log it.

```
var myObj = {
  company: "Galvanize",
  age: 3,
  categories: "Education"
};

// answer
console.log(JSON.stringify(myObj));

```
__MISC__

* Describe what DNS is.

```
Service that assigns names to IP addresses.
```

* In the terminal, type `man curl`.  Look at the man page for curl.  What do the following flags do? `-v`, `-X`.  (Hint: to search for a string, type `/` then the text you want, then enter.  To quit the man page, type `q`).

```

- specifies a Request
-v stands for verbose output

```

* What is TCP/IP?  How does it interact with HTTP?

```

TCP/IP is the protocol stack that is underlying Internet routing. It's what specifies how to reliablyy transport data to the correct location. 

```

* Does HTTP break the data that is being sent into small packets?  If not, what protocol is responsible for it?

```
No, TCP/IP is responsible for that.
```

