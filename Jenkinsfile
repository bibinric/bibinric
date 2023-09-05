pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Checkout your code from the version control repository
                checkout scm
            }
        }
        
        stage('Build') {
            steps {
                // Compile your Java code
                sh 'javac HelloWorld.java'
            }
        }
        
        stage('Test') {
            steps {
                // You can add your testing commands here if needed
            }
        }
        
        stage('Deploy') {
            steps {
                // You can add your deployment commands here if needed
            }
        }
    }
}
