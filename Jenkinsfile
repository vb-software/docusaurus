pipeline {
    agent any

    stages {
        stage('Build and Deploy') {
            steps {
                // Build and deploy the Docker image using Docker Compose
                sh 'docker-compose up -d --build'
            }
        }

        // Optional cleanup of unused Docker images
        stage('Cleanup') {
            steps {
                sh 'docker image prune -f'
            }
        }
    }

    post {
        success {
            echo 'Deployment succeeded!'
        }
        failure {
            echo 'Deployment failed.'
        }
    }
}
