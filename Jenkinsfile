pipeline {
    agent any  

    environment {
        DOCKER_HUB_CREDENTIALS_ID = 'abdurehman20'  // ID of your Docker Hub credentials stored in Jenkins
    }

    stages {
        stage('Checkout Code') {
            steps {
                git branch: 'master', url:'https://github.com/NUCESFAST/scd-final-lab-exam-abdurehman2.git'
            }
        }

        stage('Build and Push Docker Images') {
            steps {
                script {
                    // Login to Docker Hub
                    docker.withRegistry('https://index.docker.io/v1/', DOCKER_HUB_CREDENTIALS_ID) {
                        // Build the Docker images
                        sh 'docker-compose build'
                        // Push the Docker images to Docker Hub
                        sh 'docker-compose push'
                    }
                }
            }
        }
    }
}