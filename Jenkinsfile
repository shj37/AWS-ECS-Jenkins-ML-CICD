pipeline {
    agent any
    environment {
        DOCKERHUB_CREDENTIAL_ID = 'mlops-jenkins-dockerhub-token'
        DOCKERHUB_REGISTRY = 'https://registry.hub.docker.com'
        DOCKERHUB_REPOSITORY = 'juianba/mlops-proj-01'
    }
    stages {
        stage('Clone Repository') {
            steps {
                // Clone Repository
                script {
                    echo 'Cloning GitHub Repo...'
                    checkout scmGit(branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[credentialsId: 'mlops-git-access-token', url: 'https://github.com/shj37/AWS-ECS-Jenkins-ML-CICD.git']])
                }
            }
        }
        stage('Lint Code') {
            steps {
                // Lint code
                script {
                    echo 'Linting Python Code...'
                    sh 'python3 --version'
                }
            }
        }
        stage('Test Code') {
            steps {
                // Pytest code
                script {
                    echo 'Testing Python Code...'
                }
            }
        }
        stage('Trivy FS Scan') {
            steps {
                // Trivy Filesystem Scan
                script {
                    echo 'Scannning Filesystem with Trivy...'
                }
            }
        }
        stage('Build Docker Image') {
            steps {
                // Build Docker Image
                script {
                    echo 'Building Docker Image...'
                }
            }
        }
        stage('Trivy Docker Image Scan') {
            steps {
                // Trivy Docker Image Scan
                script {
                    echo 'Scanning Docker Image with Trivy...'
                }
            }
        }
        stage('Push Docker Image') {
            steps {
                // Push Docker Image to DockerHub
                script {
                    echo 'Pushing Docker Image to DockerHub...'
                }
            }
        }
        stage('Deploy') {
            steps {
                // Deploy Image to Amazon ECS
                script {
                    echo 'Deploying to production...'
                    }
                }
            }
        }
    }
