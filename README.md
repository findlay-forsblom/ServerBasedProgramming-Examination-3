# ff222ey-examination-3

### Url to the Application
The url to my application is https://cscloud702.lnu.se

## Making the Application secure

### Routes protection
Routes that should only be accessed if a user is authenticated or logged in are checked by a middleware to ensure that they are actually logged in
### Csurf protection
To minimize the risk of a csurf attack, A token is generated on each request and sent to the client which the client then sends in each post request. If the token does not match or the token is missing the server sends a 403 to the client.
### CSP
Using a module called Helmet js i was able to set a content security policy for which scripts are allowed to run on the server. This reduces the risk of XSS attacks.
### HTTPS
Instead of using normal HTTP i used https which creates a secure connection between the server and the client. Since HTTPS uses TLS it also provides message authentication and message verification so you can be certain that the sender or receiver is who he says is and that the message has not been tampered with while on transfer.
### Hooks
Using a module called express-github-webhook i was able to verify that the hooks i receive actually come from github. I pass it a secret and it does a hash och the body and it makes sure that the hash matches the x-hub signature or it throws an error.
## Terms explanations
### Reverse Proxy
A reverse proxy acts as a load balancer. It takes request from the internet and then forwards them to one of the web servers behind the proxy as can be seen in the picture below
![Minion](https://www.linuxbabe.com/wp-content/uploads/2016/01/reverse-proxy-1.png)
With a normal proxy the web server does not know what client it is talking to, With a reverse proxy it is the other way round the client does not know the actual Back end web server that is communicating with

### Process Manager
A process manager is a tool that constantly monitors a process to ensure that the process or script runs continuously
### Tls certificates
TLS stands for Transport Layer Security and it is a security protocol that provides privacy and data integrity over. In order to use tls one needs a certificate. A certificate can be gotten in two ways, A self signed one which is generated by yourself or one from a CA. If it is gotten from a CA it is then important that the CA is a trusted one that most browsers recognise
### Environment Variables
An environment variable is a variable whose value is set outside of the program. It consist of a key value pair, and the values of the keys can be referenced at any time

## Extra modules
My extra modules are
* body-parser
* connect-redis
* cookie
* csurf
* dotenv
* express-github-webhook
* express-session
* helmet
* jquey
* moment
* passport
* passport-github2
* redis
* socket.io
* webpack

### Body-parser
It provides the ability to receive data from forms and such
### Connect-redis
I had a redis database which i used to save all the sessions. This is used to be able to connect to that database
### Dot-env
Specifies where my .env file is
### Express-github-webhook
Used for my webhook
### Express-Session
Integrated with passport to be able to create a session

### Helmet
Used for csp and to remove powered-by
### Passport and Passport-github2
Does the oath part of the authentication and creates a session for the authenticate user
### Socket.io
A lightweight version of websocket
### WebPack
For pages that have multiple client scripts I used webpack to bundle them into one file instead.












