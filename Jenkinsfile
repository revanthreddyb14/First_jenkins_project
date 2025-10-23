pipeline {
    agent any

    stages {
        stage('Clone repository') {
            steps {
                git(
                    url: 'https://github.com/revanthreddyb14/flask-docker-jenkins.git',
                    branch: 'main',
                    credentialsId: 'github-token'
                )
            }
        }

        stage('Build Docker image') {
            steps {
                sh 'docker build -t flask-jenkins-demo .'
            }
        }

        stage('Run Container') {
            steps {
                sh 'docker run -d -p 5000:5000 --name flask-demo flask-jenkins-demo || true'
            }
        }
    }
}
