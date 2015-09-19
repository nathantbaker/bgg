# bgg
Board Game Geek Collections app

## Setup
* Install RabbitMQ
* Install MongoDB
* Install Node.js/npm
* git clone this repo
* run `npm install` in the repo's directory

### Automated Setup

You have a few options for automated setup:

Linux/Mac OSX:

If you have Vagrant and Ansible installed, you can run the following comands to setup:

```
npm install
ansible-galaxy install nodesource.node
grunt create-vm
```

and when you want to deploy to it after making changes:

```
grunt deploy-vm
```

Windows:

Chocolatey install coming soon.

## Start the Server
```
grunt server
```

This will run both the collection processor (RabbitMQ based message queue) and the web server (express js)

Then visit the site locally at http://localhost:7080/

Changes made to the javascript/html should cause the browser to refresh the page.

## Listen/Test Process Collection Messages
```
grunt collectionProcessor
(In another Command Line) grunt kickoffCollection
```

This will kick off a test message and process it into RabbitMQ.

What are "Collection Messages"?

BGG requires you to wait while it processes a collection request. 
A message queue is used to ensure we properly wait for BGG to finish processing.

