# Use a Jenkins image as base image
FROM jenkins/jenkins:lts

# Install Docker using the official script
USER root
RUN apt-get update -y && \
    apt-get install -y curl && \
    curl -fsSL https://get.docker.com -o get-docker.sh && \
    sh get-docker.sh

# Configure Docker to run as a non-root user
RUN usermod -aG docker jenkins

# Enable DinD
RUN mkdir -p /var/lib/docker
VOLUME /var/lib/docker