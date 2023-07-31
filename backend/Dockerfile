#setting the base image
 FROM node:14-alpine

 #setting the work directory
 WORKDIR /app/backend

#copying the package.json and lock file

COPY backend/package*.json .

#Installing the dependencies
RUN npm install

#copying the rest of the files

COPY backend .

#Exposing the port
EXPOSE 5000

#Starting the server
 CMD [ "npm", "start" ]