
pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                echo 'Jenkins has started the pipeline!'
                checkout scm
            }
        }

        stage('Build') {
            steps {
                echo 'Building the Flask application...'
                sh 'python3 --version'
                sh 'pip3 --version'
                sh 'pip3 install -r requirements.txt'
            }
        }
    }
}