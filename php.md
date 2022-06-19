PHP is a web programming platform

## Steps to setup PHP using Docker

1. Open [Docker Hub](https://hub.docker.com/) and search for PHP image. Choose the official one.
2. You need to have any source code editor, mine is using Visual Code Editor ([VS Code](https://code.visualstudio.com/download)). Have a folder in the VS Code for your project.
3. Now, let's create a Dockerfile in the project.
4. Pull the PHP image by paste this code in the Dockerfile.
   ```
      FROM php:7.4-cli
      COPY . /usr/src/myapp
      WORKDIR /usr/src/myapp
      CMD [ "php", "./index.php" ]
   ```
   COPY is going to copy all the scripts or files from the current local storage into our WORKDIR and have it run.  
   WORKDIR telling us working directory where our container is going to be stored.  
   You can change "./index.php" to any file name for the default of the page of the website  
   
5. In the index.php file, just quickly create a php script.
6. To build the image we're going to run this command in the terminal:
   ```
      $ docker build -t my-php-app .
   ```
   my-php-app is the name of the image, so you can rename it  
7. And, to run that image, we need to run anaother command:
   ```
   $ docker run -it --rm --name my-running-app my-php-app
   ```
   my-running-app going to be the name of the container     
   After you run this command, you can see it execute the script you insert before.  
      
![image](https://user-images.githubusercontent.com/106062805/174460115-4767b486-806e-4eed-b069-3685541ae650.png)  

Let's think of the way this running on the browser. So we need Apache as the web server to work with.
