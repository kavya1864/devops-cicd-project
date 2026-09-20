
pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                echo 'Checking out source code...'
                checkout scm
            }
        }

        stage('Build') {
            steps {
                echo 'Checking Python and pip...'
                sh 'python3 --version'
                sh 'pip3 --version'
                sh 'pip3 install -r requirements.txt'
            }
        }

        stage('Docker Build') {
            steps {
                echo 'Building Docker image...'
                sh 'docker build -t devops-demo-app:latest .'
            }
        }
    }
}