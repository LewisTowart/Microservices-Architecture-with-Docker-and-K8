# create a script to build an image/microservice of nodejs-app
# containerise the node app
# Use an official Node runtime as a parent image
FROM node:12
 
# Set the working directory in the container
WORKDIR /usr/src/app
 
# Copy the entire app directory to the working directory in the container
COPY . .
 
# Install the dependencies
RUN npm install
 
# Expose port 3000
EXPOSE 3000
 
# Command to run the application
CMD ["npm", "start"]
# build the image
# test the image on port 3000 locally
# if it works - push to docker hub and share image
