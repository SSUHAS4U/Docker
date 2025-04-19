pipeline {
    agent any

    environment {
        COMPOSE_PROJECT_NAME = "my_project"
    }

    stages {
        stage('Clone Repository') {
            steps {
                git 'https://github.com/SSUHAS4U/Docker.git'
            }
        }

        stage('Build Docker Images') {
            steps {
                echo 'Building Docker Images for frontend and backend...'
                sh 'docker-compose build'
            }
        }

        stage('Run Docker Containers') {
            steps {
                echo 'Running Docker containers using docker-compose...'
                sh 'docker-compose up -d'
            }
        }

        stage('Check Running Services') {
            steps {
                echo 'Checking running containers...'
                sh 'docker ps'
            }
        }
    }

    post {
        success {
            echo 'Deployment completed successfully!'
        }
        failure {
            echo 'Deployment failed. Please check logs.'
        }
    }
}
