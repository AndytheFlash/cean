# CEAN = /kiːn/ = Couchbase + Express + AngularJS + Node.js

This source code repository contains useful stuff regarding the subject 'Scaffolding modern JavaScript based web applications by using the C(ouchbase) + E(xpress) + A(ngularJS) + N(ode.js) stack'.

The CEAN stack is based on the following components:

* Couchbase Server / Couchbase Node.js module: A highly scalable distributed KV-Store and Document Database System
* Express: A web application framework for Node.js
* AngularJS: A client side JavaScript MVC web application framework
* Node.js: A JavaScript oriented web service/application platform which is designed to build scalable network application

The tooling is based on:

* YEOMAN: The web's scaffolding tool for modern webapps
* cean-cli: A node module which provides a simplified command line interface on top of YEOMAN (TODO!)

# Requirements

* Install the following on your development machine. For instance for Ubunut 14.04:
```
sudo apt-get install gcc
sudo apt-get make
sudo apt-get node
sudo apt-get npm
sudo apt-get nodejs-legacy
sudo npm install -g yo
```

# How to use

* Clone this repository
```
git clone https://github.com/dmaier-couchbase/cean.git
```
* Change the directory
```
cd cean/src/yeoman-generators/generator-cean
```
* Link the Generator by resolving the deps
```
sudo npm link
```
* Side note: Double check that you have permissions to $HOME/tmp, if not use 'chown' in order to change the owner of this directory!
* Create a new project directory 
```
cd --
mkdir myapp
```
* Scaffold a new Couchbase application
```
yo cean myapp
```
* Answer the questions regarding 'Couchbase Host', 'Couchbase Bucket', 'Couchbase Password'! Please also make sure that the bucket is existent and accessible with this password. For instance:
```
== This is the Couchbase CEAN generator ==
appname = myapp
[?] Your Couchbase Host: 192.168.7.160
192.168.7.160
[?] Your Couchbase Bucket: cean
cean
[?] Your Couchbase Bucket Password: test
test
...
```
* Wait until all dependencies are downloaded!
* Run the example application
```
node app.js
```
* Open the example application in your browser, E.G:
```
http://192.168.7.162:9000/
```
* Click on the 'Add Test Document' button
* Also inspect the log output of your application
* If everything worked fine then you get a success message:
```
Successfully added a document to your Couchbase bucket!
```
* Reload the page and you should see the just inserted message: 
```
Hello Couchbase!
```

# Screenshots
![alt tag](https://raw.github.com/dmaier-couchbase/cean/master/assets/screen.png)

# TODO-s

* Add sub-generators for controllers, ...
* Follow the 'express' folder structure which is described here: http://expressjs.com/starter/generator.html
* Add a Grunt build script which allows to run the client and server side code seperatly or together
* Wrap the yo commands by providing a cean command line tool (E.G. 'cean init $appname' instead 'yo cean $appname')
