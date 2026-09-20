
pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Docker Build') {
            steps {
                echo 'Building Docker image...'
                sh 'docker build -t devops-demo-app:latest .'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying application...'
                sh '''
                    docker stop devops-demo || true
                    docker rm devops-demo || true

                    docker run -d \
                        --name devops-demo \
                        -p 5000:5000 \
                        devops-demo-app:latest
                '''
            }
        }
        
stage('Test') {
    steps {
        echo 'Testing deployed application...'
        sh 'curl -f http://localhost:5000/'
    }
}
    }
}