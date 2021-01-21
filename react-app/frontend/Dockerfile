# Base image
FROM node:alpine as builder

# WORKING DIRECTORY
WORKDIR '/app' 

#DEPENDENCIES`
COPY package.json .
RUN npm install

#Copy sources
COPY . .

#RUN CMD
RUN npm run build

FROM nginx
COPY --from=builder /app/build /usr/share/nginx/html