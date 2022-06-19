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

//stop container
![image](https://user-images.githubusercontent.com/106062805/174465069-d4e9b84d-b118-41f9-b2a2-c2807c9f31a0.png)

//create composer
![image](https://user-images.githubusercontent.com/106062805/174465181-c3d3f89d-ceef-4d67-9a86-ac25f0b6e931.png)

//create new file for src and put index.txt to src file

//compose
![image](https://user-images.githubusercontent.com/106062805/174465199-05f91bd2-d930-45e0-a124-dc1f37ab3e32.png)

//compose running
![image](https://user-images.githubusercontent.com/106062805/174465210-90d4c8e2-b4af-467c-a7bc-cfae3b3e0695.png)


![image](https://user-images.githubusercontent.com/106062805/174465598-eacf0f82-b611-47a7-a592-95a8165258ea.png)

![image](https://user-images.githubusercontent.com/106062805/174465606-f21adc8c-e1a3-4a8d-81ef-7187398283bd.png)

//localhost:8080 - mysql
![image](https://user-images.githubusercontent.com/106062805/174465613-1ab2d7da-c213-4430-86eb-f084266f0bd6.png)


