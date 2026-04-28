pipeline {
    agent any

    stages {

        stage('Build') {
            steps {
                echo 'Building Docker Image...'
                sh 'docker build -t flask-jenkins-app .'
            }
        }

        stage('Test') {
            steps {
                echo 'Testing Application...'
                sh 'docker run -d -p 5001:5000 flask-jenkins-app'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying Application...'
                sh 'docker run -d -p 5002:5000 flask-jenkins-app'
            }
        }
    }
}