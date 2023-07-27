[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-24ddc0f5d75046c5622901739e7c5dd533143b0c8e959d652212380cedb1ea36.svg)](https://classroom.github.com/a/nj7iw4Wb)

# Prerequisites
- Docker installed on your system.
- Visual Studio Code installed on your system.

# Step 1: Prepare your Node.js Application
Ensure that you have your Node.js application files inside a directory named "nodejs_project" (replace this with your actual project folder name).

# Step 2: Create a Dockerfile
Inside the "nodejs_project" directory, create a file named "Dockerfile" (with no file extension) using a text editor. This file will contain instructions to build a Docker image for your Node.js application.

Open the "Dockerfile" and add the following content:
![alt text](https://github.com/RevoU-FSSE-2/week-6-Hillmifp/blob/main/dokumentasi/Dokumentasi%20(7).png?raw=true)

# Step 3: Build the Docker Image
Now, open Visual Studio Code and navigate to the "nodejs_project" directory.

Open the integrated terminal in Visual Studio Code and run the following command to build the Docker image:
![alt text](https://github.com/RevoU-FSSE-2/week-6-Hillmifp/blob/main/dokumentasi/Dokumentasi%20(6).png?raw=true)

# Step 4: Run the Docker Container
With the Docker image built, you can run a Docker container based on that image.

In the integrated terminal
![alt text](https://github.com/RevoU-FSSE-2/week-6-Hillmifp/blob/main/dokumentasi/Dokumentasi%20(5).png?raw=true)

# Step 5: Access the Running Application
With the container running, you can access your Node.js application at http://localhost:3001 (assuming your application is running on port 3000 inside the container). If your Node.js application is listening on a different port, map the container port to a port on your host system using the -p flag.
![alt text](https://github.com/RevoU-FSSE-2/week-6-Hillmifp/blob/main/dokumentasi/Dokumentasi%20(4).png?raw=true)
