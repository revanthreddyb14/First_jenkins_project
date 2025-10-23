pipeline {
    agent any

    stages {
        stage('Clone repository') {
            steps {
                git 'https://github.com/<your-username>/flask-docker-jenkins.git'
            }
        }

        stage('Build Docker image') {
            steps {
                sh 'docker build -t flask-jenkins-demo .'
            }
        }

        stage('Run Container') {
            steps {
                sh 'docker run -d -p 5000:5000 --name flask-demo flask-jenkins-demo'
            }
        }
    }
}

