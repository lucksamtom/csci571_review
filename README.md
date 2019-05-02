571_EXAM

# Cookie & privacy
* type of cookie
    * Session
    * Persistent
    * client-side
    * server-side
    * third-party cookie
* 6 ways to opt out of 
    * select “do not track” in browser setting
    * use browser add-ons
    * view current cookie and delete
    * use cookie management tool in browser
* Elements
    * name
    * value
    * path
    * expiration date
    * Secure: only send over SSL
    * HttpOnly: only send via HTTP request, not accessible to script in JS
* 3rd Party Cookie
    * the domain of cookie is different from the one in address bar
* 4 parties in web advertising
    * Advertiser
    * ad network
    * visitors
    * website owners
* conversion tracking cookie
    * A cookie set when you click an ad delivered by Google, used by advertisers to track when a click results in a purchase
* Define XSS (Cross Site Scripting)
    * A web security violation that enable attackers to inject client-sider scripts into web pages
* Define CSRF (Cross Site Request Forgery)
    * An attack that forces an end user to execute unwanted actions on a web application in which they’re currently anthenticated
* Q5: Is it possible to send a virus in a cookie? NO
* Anonymous is an international group of criminal hackers who have shut down many websites
 
```
function setCookie(name, value, expireDate) {
 document.cookie=name + "=" + escape(value) + "; path=/; expires=" + 
expireDate.toGMTString(); }
```
 
```
function getCookie(name) { 
var re = new RegExp(name + "=([^;]+)"); 
var value = re.exec(document.cookie); 
return (value != null) ? unescape(value[1]) : null; }
```
 
# Web Security Questions


* “weak” password recovery validation
    * Information Verification: phone, email, which are public
    * Password Hints
    * Secret Question + Answer: where born, social media
* JSON Array vulnerable to
    * Javascript Hijacking
* Two techniques used to bypass the same-origin policy.
    * JSON and the Dynamic Script Tag
    * JSONP
    * AJAX Proxy
    * IFRAME
    * CORS
    * Browser Extensions and plugins
* What used to be the problem of Domain Keys Identified Mail (DKIM) as implemented by Google Mail?
	* DKIM keys were too short and could be factored in 24 hours using a notebook.
* What is the TLD used on the “deep web”?
	* .oinion
* What combination of 2 tools adds an extra layer of encryption and anonymity making it virtually impossible to trace a user on the Web?
	* VPN and TOR
* At which point a TOR path becomes “unencrypted”?
	* the “exit node” to the target web site.
* What is the main functionality of TOR?
	* TOR is a network that provides an **anonymous path** between a client and a server
* Who has been the major target, by “size pf breach”, of top corporate hacks?
	* Yahoo
* Define, in a sentence, DDoS.
	* Distributed Denial of Service, occurs when a system is overwhelmed by malicious electronic traffic.
* Name 2 of the top 5 vulnerabilities according to WhiteHat Security?
	* Cross-site scripting (XSS)
	* Information Leakage
	* Cross-Site Request Forgery (CSRF)
	* Content Spoofing
	* Brute Force
* Name 2 types of Authentication Attacks?
	* Brute Force Attack
	* Week Password Recovery Validation
	* Insufficient Authentication
* What is a recent technique to construct highly secure passwords?
	* create long passphrases using Diceware
* What problem Diceware solves?
	* One with high degree of randomness
* Name 2 examples of Client Side Attacks?
	* XSS
	* Clickjacking
	* Browser and Plugin Vulnerabilities
* What functionality do PGP and S/MIME provide?
	* **Encryption and signing** of e-mail messages
* Why are browser plugins inherently insecure?
	* Because they bypass the browser sandbox, and can execute arbitrary malicious code
* What software library is vulnerable to the Heartbleed Bug?
	* OpenSSL
* What type of attack is Stuxnet?
	* a worm
* Name one of the most recommended way to generate strong passwords?
	* Using a very large number of characters
	* Use Diceware generated passwords
* In Public Key Encryption, when used for “privacy,” who generates the private and pubic keys? The sender or the receiver of the cipher text?
	* The Receiver
* What is a “message digest” and where is it used?
	* A Message digest is the number produced by applying a cryptographic **hash function** to a message and it is used in **digital signatures**
* List one role of a Certificate Authority (CA).
	* Guarantees that the organization is legitimate
	* Verifies the identity of an entity (client / server / e-mail address)
	* Issues digital certificates
* SSL Protocal fits between which two layers
	* TCP and HTTP
* What are RC2, RC-40 and DES examples of?
	* Bulk ciphers
* Given a data item X, and a hash function H, what is another name for H(X)?
	* A “message digest” or a “digital signature”.

* Cross-Site Scripting

```
<script> 
var user_list = <%= @users.to_json %>; 
</script>
email = "fake@email.com\"}; alert(‘Gotcha!’); //"
```
* Cross-Site Request Forgery (CSRF)

```
<img src="https://bank.com/transfer?amount=1000&to=987654321" />
```
* SQL Injection

```
before:

SELECT * FROM users WHERE username = ‘${username}’ AND Password = ‘${password}’;

username= "jsmith” OR 1 = 1; —-“ password = "blank"

after:

SELECT * FROM user WHERE username = ‘jsmith’ OR 1 = 1; —-‘ AND Password = ‘blank’;
```
* URL Manipulation

```
http://yoursite.com?SESSIONID=AG88HNG96BGF985
```

* Why the RSA algorithm cannot be used for encrypting data on Web?
	* Because it is too slow, as it involves complex mathematical calculations involving prime number (“slow” is enough)
	* List one of the major difference between a “bulk cypher” and RSA?
	* 1) Bulk cyphers use the same key for encrypt/decript –OR- 2) bulk cyphers are fast
* List two well-known cryptographic hash functions
	* MD5
	* SHA-1
	* SHA-2
* In SSL
	* Authentication of both parties is done using **Digital Certificates**
	* Message integrity is accomplished using **Message Digests**
* What are “brute force attacks”?
	* automated processes of trial and error used to guess a person’s username, password, session id or authentication cryptographic keys
* What are 2 easy ways to avoid “brute force attacks”?
	* limit the amount of unsuccessful logins t
	* block IP addresses where consecutive trial and errors
* Name one of the two ways to reduce the threat of Cross-site Scripting (XSS)?
	* Use escaping schemes like HTML entity encoding,
	* Tie session cookies to the IP address of user that originally logged in and only permit that IP to use the cookie



# High-Performance Websites Questions

* List one role of a Certificate Authority (CA).
	* Guarantees that the organization is legitimate
	* Verifies the identity of an entity (client / server / e-mail address)
	* Issues digital certificates

```
uF(this.L,this.Q,new G(b[a].x,b[a].y));var 
c,d,e,f=$L(this,a),g=aM(this,a);e=b=c=d=0;
```

* What Rule is this code an example of?
	* Minification of Javascript
* Why should you make JavaScript and CSS external?
	* Because both can be cached
* Why using a large number of hostnames in a web page is not good for performance?
	* Because each hostname may involve a time-consuming DNS lookup
* When is the use of ETags not recommended?
	* When using **"farms"** of Apache servers.
* What is the interaction between favicon.ico and cookies and how do you optimize it?
	* Each time the browser requests this file, the root cookies are sent, so they should be small	
* Where should you put style sheets and why to optimize performance?
	* At the top, because IE blocks rendering of the page until all style sheets have been examined.
* Where should you put scripts and why to optimize performance?
	* At the bottom, because scripts **block** everything from rendering **below** them in the page
* Should a web server compress images? If yes or no, elaborate why.
	* No, already compressed
* Should you scale images or not, and why?
	* No, because 1) **rescaling** in the browser is **time consuming** and 2) sending an image larger than needed **transfers more bytes** than necessary
* What are the two (2) rules (of the initial 14 Souders/Theurer rules) that minimize the transfer of information between server and browser?
	* Compression and JavaScript Minification
* What does CDN stand for and how does it improve website performance?
	* Content Distribution Network; it improves performance by copying content to multiple servers around the world so pages are delivered more quickly.
* Why is it suggested to minimize re-directs?
	* because they require an additional trip to the server and back again.
* 14 ways to improve the download performance of a website
	* Make fewer http requests 
	* Use a CDN 
	* Add and expires header 
	* Gzip components 
	* Put stylesheets at the top 
	* Move scripts to the bottom 
	* Avoid CSS expressions 
	* Make JS and CSS external 
	* Reduce DNS lookups 
	* Minify JavaScript 
	* Avoid redirects 
	* Remove duplicate scripts 
	* Configure Etags 
	* Make AJAX cacheable
* What percentage of the end-user response time is spent in the front-end?
	* 80% - 90%
* List 2 ways that reduce the number of HTTP requests? 
	* Combine scripts 
	* Combine Style Sheets 
	* Use image maps 
	* Use CSS Sprites
* What 5 types of files should be GZIP-ed (i.e. compressed)?
	* HTML, CSS, Javascript, XML, JSON
* What 2 types of files should not be GZIP-ed?
	* Image, PDF
* Speed Up HTML
	* Gzip components 
	* Move scripts to the bottom 
	* Make CSS external 
	* Make JS external
* Reduce HTTP requests
	* Combine JS Scripts 
	* Combine CSS style sheets 
	* Combine images into image maps 
	* Combine images into “sprites”
* Improve Caching
	* Expires header 
	* Cache-Control header 
	* Last-Modified header 
	* Etag header
* CSS sprites beneficial
	* Using image sprites reduces the number of HPPT requests
* POST sends the header and the data separately.
* HTML:
	* Gzip components 
	* Move scripts to the bottom 
	* Make CSS external 
* Caching
	* Add an Expiry header 
	* Configure Etags
* When estimating Web Server performance requirements, what are the three numbers that you should be estimating?
	* number of clients that will connect per second (the “traffic”)
	* average number of bytes sent to the server (request)
	* average number of bytes sent to the client (response)
* What is a web server “farm”?
	* Multiple server with load balancing hardware to distribute web requests (“the “load”) across the servers.
* What is the approach used by sites like CNN for Load Balancing?
	* DNS Redirection
* What are the 2 main reasons that Nginx is recommended for high traffic sites.
	* a) “low” memory usage and b) “large” number of requests per second for large concurrent connections (high traffic).
* List two ways of improving Apache performance.
	* Add additional RAM,
	* Enable HTTP compresions
	* Tune MinSpareServers and MaxSpareServers
	* Use Nginx as reverse-proxy
	* Use “fast:” modules liker mod_fastcgi
	* Use “direct” modules like mod_php
	
	
# HTML5

* In a \<canvas\> element what is the purpose of the “id” attribute?
	* to obtain the “drawing context” using getContext()
	
* Elements Added
	* header, footer, nav, article, section, aside, 
* Elements Removed
	* center, font, applet, frameset
* What is the required attribute of the \<video\> element in HTML5, when the video is in a single format?
	* src
* What are Quicktime (.MOV) and Flash (.FLV) files?
	* video “containers”
* Which of the following are new in HTML5?
	* [X ] video and audio support 
	* [X ] graphics support 
	* [X] local storage 
	* [ ] SQL support 
	* [X ] Geocoding support 
	* [X ] Semantic elements 
	* [X ] CSS3 support
	* [X] Sectioning elements 
	* [X] Forms validation
	* [X] Offline Support
* Which of the following capabilities are included in HTML5?
	* [ ] drag file in browser 
	* [ ] interactive canvas gradient
	* [ ] editable content 
	* [ ] geolocation 
	* [ ] drag and drop 
	* [ ] storage 
	* [X] ALL OF THE ABOVE
* What happened to the HTML 4.01 elements \<center\> and \<font\> in HTML5?
	* They have been moved to CSS
* Name 4 Audio Codecs
	* Any 4 from MP3, AAC, AAC+, VORBIS, FLAC
* What is the benefit of using AAC vs. MP3 codec encoding?
	* AAC provides support for up to **48 channels of sound** (including surround sound) while MP3 only provides **2 channels: left and right.**
* Video files format could be viewed on the large majority of browsers
	* MPEG4 and WebM
* Name 4 types of video “containers”?
	* MPEG4 (mp4 or m4v) 
	* Quicktime (.mov) 
	* Flash (.flv) 
	* Ogg (.ogv) 
	* WebM 
	* Audio Video Interleave (AVI)
* Name two popular HTML5 video codecs?
	* H.264, 
	* H.265, 
	* Theora, 
	* VP8,
	* VP9 (aka WebM), 
	* Sorenson Spark
* What is the meaning of the “autoplay” attribute?
	* Specifies that the video will start downloading and playing as soon as possible after the page loads.
* What is the purpose of the different “profiles” included in the H. 264 video standard?
	* each profile defines a set of “optional features” that trade complexity for file size.
* What is the meaning of the “preload” video attribute?
	* specifies that the video will be loaded at page load and ready to run when pressing “play”.
* In HTML5 is it possible to perform “document editing” just using HTML elements and attribues?
	* No, JavaScript code using the HTML5 Document Editing API is required.
* Why have FRAMES been removed from HTML5?
	* Frames have been removed from HTML5 because their usage affected usability and accessibility for the end user in a negative way in HTML4
	
# JavaScript Frameworks, Libraries & Serverless

* Which of the following are TRUE of **React**?
	* [X] ReactJS is a “view layer library 
	* [ ] ReactJS is a framework like AngularJS 
	* [ ] ReactJS implements MVC 
	* [X] Using ReactJS it is easy to mix HTML and JavaScript 
	* [X] React Native allows to build iOS apps 
* What is JSX?
	* JavaScript XML, a syntax extension to JavaScript
* Which of the following are TRUE of **Firebase**?
	* [X] Is a cross platform set of tools 
	* [X] Includes functionality for authentication 
	* [ ] Includes functionality for data mapping 
	* [ ] Requires the use of a GCP project
* Which of the following are TRUE of **Node.js**?
	* [X] Is a JavaScript runtime built on Chrome V8 
	* [ ] Uses blocking IO model 
	* [X] Includes modules that handle HTTP 
	* [ ] Includes modules that handle IP 
	* [X] Is bundled with ‘npm’ 
	* [X] Is a JavaScript runtime built on Chrome V8 
	* [X] Is event-driven 
	* [X] Uses non-blocking I/O model 
	* [X] Modules handle HTTP 
	* [X] Modules handle networking 
	* [X] Provides POSIX File I/O 
	* [X] Is supported by AWS and Google Cloud Platform (GCP)
* Name two properties of **Node.js**?
	* Javascript runtime built on Chrome V8Event driven 
	* Uses non-blocking IO model 
	* Modules handle HTTP 
	* Modules handel networking 
	* Provides POSIX File IO
	* Supported by both AWS and GCP
* Name 2 platforms for serverless architectures.
	* Any 2 of AWS Lambda, GCP Functions, Azure Functions, and IBM OpenWhisk
* Which JavaScript Framework provides two-way Data Binding?
	* **AngularJS**
* What directive is used in **AngularJS** for loop and replication of the template to the number of rows in the model?
	* `ng-repeat`
* What architectures are supported by **AngularJS**
	* MVC (Model – View - Controller)
	* MVVM (Model – View – ViewModel)
	* 
* What are the two problems with **Virtual Machines** and why?
	* Money – You need to predict the instance size you need. You are charged for every CPU cycle, even when the system is “running its thumbs” l 
	* Time – Many operations related to **virtual machines** are typically slow
* What are two solutions of the problems with **Virtual Machines**?
	* **Serverless Architectures** and **Containers**
* What are the 3 components of a **Microservice**?
	* An API – OR – **REST Endpoint**
	* A Service – OR – **FaaS** (Function as a Service)
	* A Data Store
* Which of the following are true of **Serverless** Architectures?
	* [X] No compute resource to manage 
	* [ ] Provisioning and scaling handled by the client 
	* [X] Execution environment provided by service 
	* [X] Provides authorization and authentication services
* Which of the following are true of **AWS Lambda**?
	* [X] No servers to manage 
	* [X] Continuous scaling 
	* [ ] Subminute metering 
	* [X] bring your oen code 
	* [ ] Complex resource model 
	* [X] Flexible Authorization and Use 
	* [ ] Not suitable for real-time data processing 
	* [X] Easy to build scalable backend services

```
module.exports.handler = function(event, context, callback) { 
console.log("event: " + JSON.stringify(event)); 
if ((!event.hasOwnProperty("email") || !event.hasOwnProperty("restaurantId")) || (!event.email || !event.restaurantId)) { 
callback("[BadRequest] email and restaurantId are required");
return; } }
```

* What is the code below an example of?
	* Node.js with AWS lambda
	* FaaS (Function as a Service)
* Which of the following is true of AWS lambda?
	* [X] Uses AWS Compute Service 
	* [X] Supports Java, Python and Node.js 
	* [X] You pay only for the compute time you use 
	* [ ] Can be triggered by HTTP only 
	* [X] No machines or VMs are visible in the Programming Model 
	* [X] It auto-scales and is layaways available 
	* [X] It competes with Google Cloud Platform (GCP)
* Does Google Cloud Platform (**GCP**) supports both **Microservices** and **Containers**?
	* No, supports Only **Microservices**.

```
exports.helloGET = function helloGET (req, res) { 
res.send('Hello World!');
```

* What is this code an example of?
	* A Google Cloud Function

```
<script> var app = angular.module(“myApp", []); 
app.controller(“myController", function($scope,$http) {

$scope.topic = “CSCI 571”;

}); 
</script> 
<body ng-app=“myApp" ng-controller=“myController"> </body>
```

* Which of the following is true in **AngularJS**?
	* [X] A module defines an application 
	* [X] A module is a container for controllers 
	* [X] Controllers always belong to a module 
	* [ ] Filter sorts the rows in the model 
	* [X] ng-repeat works like a for loop 
	* [X] $http holds the HTTP request handler
* What is **AngularJS** good for?
	* **AngularJS** is good for declaring **“dynamic views”** in web applications
* What layer of the **MVVM** pattern is Vue.js focused on?
	* The ViewModel layer

	



# Responsive Website Design Questions


```
<div class="row"> 
	<div class="col-md-4">.col-md-4</div> 
	<div class="col-md-4">.col-md-4</div> 
	<div class="col-md-4">.col-md-4</div> 
</div>
```

* What library is this code using and for what kind of layout?
	* **Bootstrap** library and **Grid Layout**
* Name the three “concepts” that are the basis of Responsive Website Design?
	* **fluid grids**
	* **flexible images**
	* **CSS3 Media Queries**
* What is the CSS code (property and value) to hide content on small screens?
	* display: none; -OR- visibility: hidden;
* Please write an example of a media query.
	* `<link rel="stylesheet" type="text/css" media="screen and (max-device-width: 480px)" href=“min.css" />`
* List one property of “fluid” grids.
	* defined using relative-based dimensions
	* define a grid divided into a specific number of columns 
	* each grid element is designed with “proportional” width and height, not in pixels
* Mention one reason why hosting a separate **.mobi** website is not recommended?
	* Requires duplication of content
	* Over time can result in synchronization of content issues
	* May work only on a specific mobile size
* Why hosting a **mobile website** within your current domain (m.mycompany.com) is not recommended?
	* Redirect take time
	* Redirect and hinder search engines
	* May work only on a specific mobile size
* How do you implement “flexible images” in RWD?
	* `img {max-width: 100%}`

```
.sidebar { float: right; width: 250px; } .complicatedFunctionality {

background-image: url('img_flowers.jpg'); lots of CSS settings }

@media all and (max-device-width: 600px) { 
.complicatedFunctionality { display: none; } 
.sidebar { float: none; width: auto; } 
}
```

* What are 2 problems with the above code on devices with width < 600 pixels?
	* The browser will download all of the CSS, even the one that is not used
	* Even images that are hidden, will be downloaded
* What is the main difference between **“adaptive”** and **“fluid”** grids?
	* **fluid grids** we define relative-based dimensions; 
	* **adaptive grids** we define pixel-based dimensions.



	

# Javascript & AJAX

# jQuery



# Agile

* What is the difference between waterfall and agile development regarding “testing” a software application?
	* **waterfall**: test late 
	* **agile**: test early and continuously
* In **Agile** Development what is the difference between **“pigs”** and **“chickens”**?
	* **pigs** are the “scrum team”, that have deliverables in the sprint and
	* **chickens** are “observers”, that do not have deliverables in the sprint