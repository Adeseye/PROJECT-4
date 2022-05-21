### MEAN STACK DEPLOYMENT TO UBUNTU IN AWS

The last 3 projects I deployed LAMP,LEMP and MEARN Web stack. In this project I will be deploying MEAN stack on to Ubuntu Server.

### Prerequisites:
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


