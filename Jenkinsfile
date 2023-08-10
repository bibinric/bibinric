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
                    sh 'docker build -t my-docker-image:latest -f Dockerfile .'
                }
            }
        }
    }
}
