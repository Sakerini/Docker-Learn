# Simple WebApp

This is a simple webapp to demonstrate how to use docker to run your applications.

- Simple **NodeJS** webapp that has one get method which returns a string.
- **Package.json** with all the dependencies. (For this example we need only express)
- **Awesome** Dockerfile 🌟 with docker configuration build.

## Example
```js
# Base image
FROM node:alpine

# WORKING DIRECTORY
WORKDIR /usr/app

#DEPENDENCIES
COPY ./package.json /usr/app
RUN npm install

#Copy sources
COPY ./ /usr/app

# Default Cmd
CMD ["npm", "start"]	
```
Here we use **node:alpine** as a base image for our docker configuration.
We use **node** because in this public image it has **node package manager** installed already.
**alpine** is the most compact version of node docker image offered. Usually every public image will be offered with **alpine** version.

We specify **WORK DIRECOTRY** so that we wont get in any conflicts with system files and overwrite them while copying.

Copying **package.json** to our working directory is important before we run **npm install** command. After that our projects is set and ready for soruce files. Copying sources.

At last we set Default CMD when we use **docker run**.

## Usage
When we start our application we have to set ports.

**Example** -- docker run -p 5050:8080 sakerini/simpleweb
This will mapp port of localhost:5050 to container's 8080 port
access is now available at localhost:5050

**Example** -- docker run -p -it 5050:8080 sakerini/simpleweb sh
This command will open conatiners shell we can use for debugging or etc. We can start application by using node index.js


------

