pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                git branch: 'Mayuri', url: 'https://github.com/Mayuri3329/DevOpsLab.git'
            }
        }

        stage('Build') {
            steps {
                echo 'Building application...'
            }
        }

        stage('Test') {
            steps {
                echo 'Running tests...'
            }
        }

        stage('Docker Build') {
            steps {
                bat 'docker build -t jenkins-docker-demo .'
            }
        }

        stage('Docker Run') {
            steps {
                bat 'docker stop demo-container || exit 0'
                bat 'docker rm demo-container || exit 0'
                bat 'docker run -d -p 8081:80 --name demo-container jenkins-docker-demo'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Application deployed successfully!'
            }
        }
    }
}