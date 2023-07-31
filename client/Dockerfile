# Base image
FROM node:14-alpine

# Setting the  working directory
WORKDIR /app/client

# Copying the  package.json and lock files to the current working directory
COPY client/package*.json ./

# Installing only the necessary  dependencies
RUN npm install

# Copying  the rest of the client files
COPY client .

# Expose the client port (if necessary)
EXPOSE 3000

# Start the client development server
CMD ["npm", "start"]
