PHP is a web programming platform

## Steps to setup PHP using Docker

1. Open [Docker Hub](https://hub.docker.com/) and search for PHP image. Choose the official one.
2. You need to have any source code editor, mine is using Visual Code Editor ([VS Code](https://code.visualstudio.com/download)). Have a folder in the VS Code for your project.
3. Now, let's create a Dockerfile in the project.

   ![image](https://user-images.githubusercontent.com/106062805/174463533-9caba716-e868-40fc-abcd-3d5db7b9f20a.png)

5. Pull the PHP image by paste this code in the Dockerfile.
   ```
      FROM php:7.4-cli
      COPY . /usr/src/myapp
      WORKDIR /usr/src/myapp
      CMD [ "php", "./index.php" ]
   ```
   COPY is going to copy all the scripts or files from the current local storage into our WORKDIR and have it run.  
   WORKDIR telling us working directory where our container is going to be stored.  
   You can change "./index.php" to any file name for the default of the page of the website  
   
   ![image](https://user-images.githubusercontent.com/106062805/174464219-1a89ef9a-e747-4470-a275-9fd85f331ccd.png)

5. In the index.php file, just quickly create a php script.

   ![image](https://user-images.githubusercontent.com/106062805/174464232-03ddc426-f1f2-4aa4-a0bc-f81aac24fb67.png)

7. To build the image we're going to run this command in the terminal:
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
      
  ![image](https://user-images.githubusercontent.com/106062805/174463722-ddcea9a1-12e8-458b-9848-16ed515ecc61.png)
  
Let's think of the way this running on the browser. So we need Apache as the web server to work with.

//create containers
![image](https://user-images.githubusercontent.com/106062805/174464047-a9554fa3-4e05-41f8-9b16-cc30095c11af.png)

//containers running
![image](https://user-images.githubusercontent.com/106062805/174464310-426a6ad9-2126-40ac-9d52-eeda9e491dd6.png)

//output - localhost:8000
![image](https://user-images.githubusercontent.com/106062805/174464449-edd9cb8c-ded4-490b-9095-570fb31aaba4.png)


