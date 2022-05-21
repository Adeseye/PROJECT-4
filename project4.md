### MEAN STACK DEPLOYMENT TO UBUNTU IN AWS

The last 3 projects I deployed LAMP,LEMP and MEARN Web stack. In this project I will be deploying MEAN stack on to Ubuntu Server.

### PREREQUISITES:
AWS Free tier account
EC2 instance of t2.nano with Ubuntu Server 20.04LTS(HVM) image. 
Installing and configuring NodeJS, MongoDB, Express JS.
Update firewall : create inbound rule for TCP port 3300

### TASK

In this project I'm going to implement a simple Book Register web form using MEAN stack.

I will be using MobaXterm to connect to my instance....Lets begin:

Step 1: Install NodeJs

Node.js is a JavaScript runtime built on Chrome’s V8 JavaScript engine. Node.js is used in this tutorial to set up the Express routes and AngularJS controllers.

Update ubuntu

<code>sudo apt update</code>

![alt text](./Images/sudo%20update.JPG)

Upgrade ubuntu

<code>sudo apt upgrade</code>

![alt text](./Images/sudo%20apt%20upgrade.JPG)

Add certificates

<code>sudo apt -y install curl dirmngr apt-transport-https lsb-release ca-certificates

curl -sL https://deb.nodesource.com/setup_12.x | sudo -E bash -
</code>

![alt text](./Images/add%20certificates.JPG)

Install NodeJS

<code>sudo apt install -y nodejs</code>

![alt text](./Images/install%20Node.JS)

Step 2: Install MongoDB

MongoDB stores data in flexible, JSON-like documents. Fields in a database can vary from document to document and data structure can be changed over time. 

For our example application, we are adding book records to MongoDB that contain book name, isbn number, author, and number of pages.
mages/WebConsole.gif

<code>
sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv 0C49F3730359A14518585931BC711F9BA15703C6
</code>

---

<code>
echo "deb [ arch=amd64 ] https://repo.mongodb.org/apt/ubuntu trusty/mongodb-org/3.4 multiverse" | sudo tee /etc/apt/sources.list.d/mongodb-org-3.4.list
</code>

---

![alt text](./Images/Json%20code.JPG)

Install MongoDB

<code>sudo apt install -y mongodb</code>

Start The server

<code>sudo service mongodb start</code>

Verify that the service is up and running

<code>sudo systemctl status mongodb</code>

Install npm – Node package manager.

<code>sudo apt install -y npm</code>

Install body-parser package

We need ‘body-parser’ package to help us process JSON files passed in requests to the server.

<code>sudo npm install body-parser</code>

Create a folder named ‘Books’

<code>mkdir Books && cd Books</code>

In the Books directory, Initialize npm project

<code>npm init</code>

Add a file to it named server.js

<code>vi server.js</code>

Copy and paste the web server code below into the server.js file.

<code>
var express = require('express');
var bodyParser = require('body-parser');
var app = express();
app.use(express.static(__dirname + '/public'));
app.use(bodyParser.json());
require('./apps/routes')(app);
app.set('port', 3300);
app.listen(app.get('port'), function() {
    console.log('Server up: http://localhost:' + app.get('port'));
});
</code>