pipeline {
    agent any
    
    stages {
        stage('Clone Repository') {
            steps {
                sh "git clone https://github.com/samsonmeseret/CI-CD-app"
            }
        }
        
        stage('Build Images') {
            steps {
                script {
                    // Navigate to the 'app' directory where your Dockerfile is located
                    dir('app') {
                        // Build the Docker image for the server API
                        sh 'docker build -t samsonmeseret/ci-cd-api:server-latest .'
                    }
                }
            }
        }
        
        stage('Start Container') {
            steps {
                // Run the Docker container using the built image
                sh 'docker run -d -p 5000:5000 samsonmeseret/ci-cd-api:server-latest'
            }
        }
    }
}