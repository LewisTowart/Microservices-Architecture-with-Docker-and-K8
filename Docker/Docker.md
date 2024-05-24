# Docker

## What is Docker

Docker is a platform that uses containerization technology to package and run applications and their dependencies in isolated environments called containers. These containers are lightweight, portable, and ensure that the software runs consistently across different computing environments. Docker simplifies application deployment, scaling, and management by allowing developers to bundle an application with all its necessary components, libraries, and configurations, making it easier to move from development to production without compatibility issues. This enhances efficiency, reduces conflicts between different systems, and streamlines the development process.

## Installing Docker

To install Docker you can view the below guide online.

https://docs.docker.com/desktop/install/windows-install/

On the guide you can see the download link for Windows Docker Desktop. Launch the installer and it will take you through the necessary steps, you will likely need to perform a restart. Follow the instructions on the installation wizard and once it's finished either sign in or make an account.

docker run hello world
can do :v8 etc after to choose version or put nothing which is latest

image is stopped exists does nothing container is running

docker client is us local host pull wont run it just download

docker ps what's running
docker ps -a

docker exec -it image sh (or do bin/bash)
docker exec -it image sh

create index.html on local host

run -d -p 90:80 my image

apt-get install sudo

docker logs 

docker rm contrainer_id (can -f)

good practice to back up the logs

ctrl c to exit locked console 

## Creating a Docker Image

File path to note /usr/share/nginx/html/

### Step 1.

First you need to create a index.html file locally which you can edit using HTML to display you webpage how you would like.

Make sure you are running the Nginx image using the below command.

```
docker run -d -p 80:80 e784f4560448
```

### Step 2.

Next we want to copy our new index file into our microservice to replace the existing web content.

```
docker cp ~/file_path e784f4560448:usr/share/nginx/html/index.html
```

### Step 3.

Now we can commit the changes to the microservice using the below command

```
docker commit <container_id>
```

### Step 4.

Now Docker would've created a new id so we can use the below command to see what images are available locally.

```
docker images -a
```

### Step 5.

We can now tag the image with a name of our choosing with the below command.

```
docker tag <img_id> <name_i_want>
```

### Step 6.

We now want to tag the image with a specific area of our repo I suggest using a new repo name for <dockerhub_repo_name> if it's something new you're working on. May have to put in the image id instead try again using the below command.

```
docker tag <image_name> <dockerhub_user_name>/<dockerhub_repo_name>:latest
```

### Step 7.

Now the new image can be pushed to your Docker Hub repo.

```
docker push <dockerhub_user_name>/<dockerhub_repo_name>:latest
```

# Creating a New Image (app)

# Step 1.

Create a new folder of which we can work from. Copy the app code either from Github or from your local device to this folder.

# Step 2.

In git bash cd in the newly created folder then into your app folder.

# Step 3.

We are going to want to create a Dockerfile here so that it is easier to copy. Run the below command.

```
nano Dockerfile
```

# Step 4.

Here is the script I used with comments explaining the sections.

```
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
```

# Step 5.

Now we want to build our new image. So in the same directory run the below command.

```
docker build -t lewistowart/nodejs-app .
```

This command is referencing my profile on Dockerhub the name of the new repo I want to create here and the . is to run the dockerfile in this directory.

# Step 6.

Now we want to run our new build to see if it actually works as intended.

```
docker run -p 3000:3000 lewistowart/nodejs-app
```

To exit this once you have check localhost:3000 to see if the app is working use ctrl C

# Step 6.

Now we can push our new image to my Dockerhub account using the below command.

```
docker push lewistowart/nodejs-app:latest
```

You should now be able to see your image in the repositories section of your Dockerhub account.

volume is a removable detachable persistent form of storage. important to consider how much volume/storage you need. like a usb drive can be attached to any instance. Multiple people can use one volume. If created locally will take the space from our hard drive.

read replica, creates data replicas just to be read as usually data only need toi be publisbed once

mount to aws, local, s3

needs to be permsistent backup of data

create vol 10

use 5

1 gb for etc


