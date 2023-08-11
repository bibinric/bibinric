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
                    docker.withRegistry(https://hub.docker.com/u/bibinrich, key_1) {
                        // Push the Docker image to Docker Hub
                        docker.image(imageName).push()
                }
                
            }
        }
    }
}
