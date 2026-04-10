pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh 'docker build -t django-polls-app .'
            }
        }
        stage('Deploy') {
            steps {
                sh 'docker stop polls-run || true'
                sh 'docker rm polls-run || true'
                sh 'docker run -d --name polls-run -p 80:8000 django-polls-app'
            }
        }
    }
}
