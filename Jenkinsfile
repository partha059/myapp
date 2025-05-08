pipeline {
    agent any
    environment {
        DOCKERHUB_USER = 'partha059'
        DOCKERHUB_PASS = 'Sarathi@05000'
    }
    stages {
        stage('Clone Repository') {
            steps {
                git 'https://github.com/partha059/myapp.git'
            }
        }
        stage('Build Docker Image') {
            steps {
                sh 'docker build -t partha059/myapp:latest .'
            }
        }
        stage('Push to Docker Hub') {
            steps {
                sh 'docker login -u $DOCKERHUB_USER -p $DOCKERHUB_PASS'
                sh 'docker push partha059/myapp:latest'
            }
        }
    }
}
