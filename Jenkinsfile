pipeline {
    agent{
        docker{

    environment {
        // Define the Docker Hub credentials
        DOCKER_HUB_USERNAME = credentials('tejasudarhan58')
        DOCKER_HUB_PASSWORD = credentials('ganesh040601')
        // Define the Docker image name and tag
        DOCKER_IMAGE_NAME = 'my-app-1.0-SNAPSHOT'
    }
        }

    stages {
        stage('Checkout') {
            steps {
                // Checkout the source code from your version control system (e.g., Git)
                checkout scm
            }
        }

        stage('Build and Push Docker Image') {
            steps {
                script {
                    // Build the Docker image
                    docker.build("${DOCKER_IMAGE_NAME}:${env.BUILD_NUMBER}")

                    // Log in to Docker Hub
                    docker.withRegistry('https://registry.hub.docker.com', 'docker-hub-credentials') {
                        // Push the Docker image to Docker Hub
                        docker.image("${DOCKER_IMAGE_NAME}:${env.BUILD_NUMBER}").push()
                    }
                }
            }
        }
    }

    post {
        success {
            echo "Docker image built and pushed successfully!"
        }
    }
}

