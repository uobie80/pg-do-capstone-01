# Microservice Application Deployment on EC2 Instance

## Introduction
This document outlines the steps involved in deploying a microservice application on an EC2 instance using DevOps methodologies.

## Objective
The objective is to establish a microservice application architecture for an insurance company using a DevOps pipeline and deploying it on Docker.

## Problem Statement and Motivation
ASI Insurance is encountering challenges in enhancing its SLA to customers due to organizational growth and the limitations of its existing monolithic application architecture. The transformation to a microservice application architecture, coupled with the implementation of DevOps pipelines and automation, is imperative.

Successful completion of the project will enable ASI Insurance to streamline its application deployment process, improve system scalability, and deliver superior products and services to its clientele.

## Software Requirements
- **Jenkins:** Utilized for continuous integration and continuous delivery to automate the software delivery process.
- **GitHub:** A web-based hosting service for managing Git repositories. GitHub facilitates source code management for microservices and supports the development process.
- **Docker Hub:** A cloud-based repository for storing, managing, and sharing Docker container images. Docker Hub is utilized to store Docker images and deploy them on the cloud.
- **Amazon Web Services (AWS):** A cloud platform providing computation and storage resources. The application will be deployed on an EC2 instance within AWS.

## Task (Activities)
1. Create the Dockerfile, Jenkinsfile, Ansible playbook, and source files of the static website.
2. Upload all created files to GitHub.
3. Install NodeJS 16 on the terminal.
4. Access the Jenkins application via the browser.
5. Create a Jenkins pipeline to perform CI/CD for a Docker container.
6. Configure Docker Hub Credentials and other prerequisites before running the build.
7. Set up a Docker remote host on AWS and configure the deployment stage in the pipeline.
8. Execute the Jenkins Build.
9. Access the deployed application on the Docker container.
