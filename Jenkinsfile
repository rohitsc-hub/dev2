pipeline {
    agent any

    stages {
        stage('Build Docker Image') {
            steps {
                bat 'docker build -t simple-web-app .'
            }
        }

        stage('Stop Old Container') {
            steps {
                bat 'docker rm -f simple-web-app || exit /b 0'
            }
        }

        stage('Run Docker Container') {
            steps {
                bat 'docker run -d --name simple-web-app -p 8081:80 simple-web-app'
            }
        }

        stage('Verify Application') {
            steps {
                bat 'docker ps'
                bat 'docker image ls simple-web-app'
            }
        }
    }
}

