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
                     def imageName = "Hellow"
                    def dockerfile = "."  // Path to your Dockerfile

                    docker.build(imageName, "-f ${dockerfile} .")
                }
                
            }
        }
    }
}
