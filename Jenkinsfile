pipeline {
    agent any

    stages {

        stage('Build') {
            steps {
                bat 'mvn clean package'
            }
        }

        stage('Docker') {
            steps {
                bat 'docker build -t webapp .'
                bat 'docker rm -f webapp-container || true'
                bat 'docker run -d -p 8087:8080 --name webapp-container webapp'
            }
        }
    }
}
