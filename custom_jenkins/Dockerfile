# Dockerfile
FROM jenkins/jenkins:lts

USER root

# Install Docker CLI (docker.io) from Debian repo
RUN apt-get update -y && \
    apt-get install -y --no-install-recommends \
      apt-transport-https \
      ca-certificates \
      curl \
      gnupg2 \
      software-properties-common \
      docker.io && \
    # Clean up apt caches to reduce image size
    rm -rf /var/lib/apt/lists/*

# Add jenkins user to docker group
RUN usermod -aG docker jenkins

USER jenkins
