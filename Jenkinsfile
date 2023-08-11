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
                     def imageName = "hello-world-docker-image1"
                     def dockerfile = "Dockerfile"  // Dockerfile in the repository root

                    // Build the Docker image
                    docker.build(imageName, "-f ${dockerfile} .")
                   // docker.withRegistry(docker.io, af11d75f-820a-4565-9332-eaf36c0484d6) {
                        // Push the Docker image to Docker Hub
                       // docker.image(imageName).push()
                }
                
            }
        }
    }
}
