Flask App Deployment with Docker & Jenkins

This project is a small end-to-end setup where I automated the build and deployment of a simple Flask web application using Docker and Jenkins.
The main purpose of this project was to learn how to reduce manual work during deployments and to understand how CI/CD pipelines actually work in practice.

Project Overview
Flask App: A simple Python Flask application (app.py) with basic functionality.
Requirements: All Python dependencies are listed inside requirements.txt.
Dockerization: I wrote a Dockerfile to package the app into a Docker image.
Jenkins Pipeline: I created a Jenkinsfile which automates:

Pulling the latest code from Git.
Building the Docker image.
Running the container.

By using Jenkins, I don’t have to manually build and run the container every time. Everything is automated with just one pipeline run.

Folder Structure
.
├── app.py
├── requirements.txt
├── Dockerfile
└── Jenkinsfile

Steps I Performed

Wrote a basic Flask app (app.py).
Added required packages inside requirements.txt.
Created a Dockerfile to build the image.
Tested the image locally with docker build and docker run.
Installed and configured Jenkins.
Created a Jenkins pipeline job and linked it with the Jenkinsfile.
Automated the whole flow so that Jenkins builds and runs the container on every run.

What I Learned

How to write and run a basic Flask application.
How Docker helps in packaging apps with all dependencies.
How Jenkins pipelines work and how they can reduce manual effort.
End-to-end flow of CI/CD for a small application.

Benefits of This Project

Reduced manual work (no need to build/run containers manually).
Clear understanding of Docker + Jenkins integration.
Hands-on experience with pipeline automation.
Future Improvements
Add automated testing before building the image.
Push Docker images to DockerHub/ECR.


This project really helped me get a practical understanding of how CI/CD pipelines are set up for even bigger projects.
