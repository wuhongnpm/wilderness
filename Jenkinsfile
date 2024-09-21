pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/wuhongnpm/wilderness.git'
            }
        }
        stage('Build') {
            steps {
                sh 'docker build -t jenkins .'
            }
        }
        stage('Deploy to K3s') {
            steps {
                sh 'kubectl apply -f deployment.yaml'
            }
        }
    }
}