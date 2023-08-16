pipeline {
    agent any
    
    environment {
        DOCKER_HUB_USERNAME = credentials('bibinrich25@gmail.com')
        DOCKER_HUB_PASSWORD = credentials('Ryan@0524')
    }
    
    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }
        
        stage('Build Docker Image') {
            steps {
                script {
                    def imageName = "bibinrich25@gmail.com/sample"
                    def imageTag = "latest"
                    def dockerFilePath = "." // Path to your Dockerfile in the repository
                    
                    // Build the Docker image
                    docker.build(imageName + ":" + imageTag, "-f ${dockerFilePath} .")
                }
            }
        }
        
        stage('Push Docker Image') {
            steps {
                script {
                    def imageName = "bibinrich25@gmail.com/sample"
                    def imageTag = "latest"
                    
                    // Log in to Docker Hub
                    docker.withRegistry('https://index.docker.io/v1/', bibinrich25@gmail.com, Ryan@0524) {
                        // Push the Docker image to Docker Hub
                        docker.image(imageName + ":" + imageTag).push()
                    }
                }
            }
        }
    }
    
    post {
        always {
            // Clean up resources if needed
            cleanWs()
        }
    }
}
