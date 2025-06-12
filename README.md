# MLOps Pipeline with Jenkins, Docker, and AWS ECS

![Project Overview](https://miro.medium.com/v2/resize:fit:1100/format:webp/1*RXD8hqmXheaJ8cxOG61XEg.jpeg)

This repository contains an MLOps pipeline for automating the deployment of a machine learning model using Jenkins for CI/CD, Docker for containerization, and AWS ECS for scalable orchestration.

## Overview

The project automates the deployment of a Flask-based ML application (Iris classification model) through a Jenkins pipeline. It emphasizes secure, repeatable workflows with code quality checks and vulnerability scanning.

## Key Features

- **CI/CD Pipeline**: Jenkins automates code checkout, linting (Pylint, Flake8, Black), testing (Pytest), and deployment.
- **Security**: Trivy scans filesystem and Docker images for vulnerabilities.
- **Containerization**: Docker-in-Docker setup builds and deploys the app.
- **Cloud Deployment**: AWS ECS with Fargate serves the model via a load balancer.

## Repository Structure

- `train.py`: Trains the ML model.
- `app.py`: Flask app for model serving.
- `Jenkinsfile`: Defines the CI/CD pipeline.
- `Dockerfile`: Builds the app’s Docker image.
- `custom_jenkins/Dockerfile`: Custom Jenkins image with Docker-in-Docker.
- `tests/`: Pytest scripts for model and app validation.

## Setup

1. Clone the repo: `git clone https://github.com/shj37/AWS-ECS-Jenkins-ML-CICD.git`
2. Set up a virtual environment and install dependencies: `pip install -r requirements.txt`
3. Build and run the Jenkins container (see [Medium article](https://medium.com/@jushijun/automating-ml-model-deployment-a-ci-cd-pipeline-with-jenkins-docker-and-aws-ecs-a7473c4cb92e)).
4. Configure AWS credentials and ECS cluster as described in the article.

## Usage

Run `python train.py` to generate the model, then `python app.py` to test locally. The Jenkins pipeline automates linting, testing, building, scanning, and deploying to AWS ECS.

**All credit to iQuant for the original project design and code.**

## Resources

- [Medium Article](https://medium.com/@jushijun/automating-ml-model-deployment-a-ci-cd-pipeline-with-jenkins-docker-and-aws-ecs-a7473c4cb92e): Detailed project walkthrough.
- [YouTube Reference](https://www.youtube.com/watch?v=MwmuwhwzGTk&t=18s): iQuant tutorial.
- https://github.com/iQuantC/MLOps01