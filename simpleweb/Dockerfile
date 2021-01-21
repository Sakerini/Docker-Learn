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