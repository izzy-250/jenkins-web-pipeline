pipeline {
    agent any

    stages {
        stage('Clone') {
            steps {
                echo "Checking out source code from GitHub..."
                bat "git status"
            }
        }
        stage('Build') {
            steps {
                echo "Building the web application..."
                bat "dir"
            }
        }
        stage('Test') {
            steps {
                echo "Running tests..."
                bat "echo Tests passed successfully"
            }
        }
        stage('Deploy') {
            steps {
                echo "Deploying web application..."
                bat "echo Deployment step completed"
            }
        }
    }
}
