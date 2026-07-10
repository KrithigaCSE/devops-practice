pipeline {
    agent any

    stages {

        stage('Clone') {
            steps {
                echo 'Getting latest code'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t studentapp:v1 .'
            }
        }

        stage('Run Container') {
            steps {
                sh 'docker rm -f studentweb || true'
                sh 'docker run -d --name studentweb -p 8080:80 studentapp:v1'
            }
        }
    }
}
