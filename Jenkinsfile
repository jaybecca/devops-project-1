pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/jaybecca/devops-project-1.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t devops-project-1 .'
            }
        }

        stage('Deploy Container') {
            steps {
                sh '''
                docker rm -f devops-project-1 || true
                docker run -d --name devops-project-1 -p 8082:80 devops-project-1
                '''
            }
        }
    }
}