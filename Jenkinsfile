pipeline {
    agent any
    
    stages {
        stage('Clone Repository') {
            steps {
                sh "rm -rf CI-CD-app"
                sh "git --version"
                sh "git clone https://github.com/samsonmeseret/CI-CD-app.git"
            }
        }
        
        stage('Build Images') {
            steps {
                script {
                                    

                    // Navigate to the 'api' directory where your Dockerfile is located
                    dir('CI-CD-app/api') {
                        // Build the Docker image for the server API
                        sh 'docker build -t ci-cd-api .'
                    }
                }
            }
        }
        
        stage('Start Container') {
            steps {
                    // Stop and remove existing container if it exists
                // Run the Docker container using the built image
                sh 'docker run -d -p 3000:3000 ci-cd-api'
            }
        }
    }
}
