pipeline {
    agent any

    environment {
        DOCKER_IMAGE = 'jenkins-web-app:latest'
        CONTAINER_NAME = 'jenkins-web-app'
    }

    stages {
        stage('Checkout') {
            steps {
                echo 'Checking out source code...'
                bat 'git status'
            }
        }
        stage('Build Docker Image') {
            steps {
                echo 'Building local Docker image...'
                bat "docker build -t %DOCKER_IMAGE% ."
            }
        }
        stage('Deploy to Local Docker Host') {
            steps {
                echo 'Deploying container on local Docker host...'
                bat "docker rm -f %CONTAINER_NAME% 2>nul || exit /b 0"
                bat "docker run -d --name %CONTAINER_NAME% -p 8081:3000 %DOCKER_IMAGE%"
            }
        }
    }
}
