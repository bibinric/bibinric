pipeline {
    agent any
    
    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }
        
        stage('Build Docker Image') {
            steps {
                script {
                     def imageName = "hello-world-docker-image"
                    def dockerfile = "Dockerfile"  // Dockerfile in the repository root

                    // Build the Docker image
                    docker.build(imageName, "-f ${dockerfile} .")
                }
                
            }
        }
    }
}
