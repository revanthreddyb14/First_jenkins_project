pipeline {
    agent any

    stages {
        stage('Clone repository') {
            steps {
                git(
                    url: 'https://github.com/revanthreddyb14/First_jenkins_project.git',
                    branch: 'main',
                    credentialsId: 'github-token'
                )
            }
        }

        stage('Build Docker image') {
            steps {
                sh 'docker build -t Dockerfile .'
            }
        }

        stage('Run Container') {
            steps {
                sh 'docker run -d -p 5000:5000 --name flask-demo Dockerfile || true'
            }
        }
    }
}
