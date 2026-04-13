pipeline {
    agent any

    stages {
        stage('Clone Code') {
            steps {
                git 'https://github.com/GSagar10/devops-nginx-cicd-project.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t devops-app .'
            }
        }

        stage('Stop Old Container') {
            steps {
                sh 'docker rm -f devops-container || true'
            }
        }

        stage('Run Container') {
            steps {
                sh 'docker run -d -p 80:80 --name devops-container devops-app'
            }
        }
    }
}
