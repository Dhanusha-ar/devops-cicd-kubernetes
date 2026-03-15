pipeline {

    agent any

    environment {
        DOCKER_IMAGE = "yourdockerhubusername/flask-app"
    }

    stages {

        stage('Clone Repository') {
            steps {
                git 'https://github.com/yourusername/devops-cicd-kubernetes.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t $DOCKER_IMAGE:latest -f docker/Dockerfile .'
            }
        }

        stage('Push Docker Image') {
            steps {
                withCredentials([string(credentialsId: 'dockerhub-password', variable: 'DOCKER_PASS')]) {
                    sh 'docker login -u yourdockerhubusername -p $DOCKER_PASS'
                    sh 'docker push $DOCKER_IMAGE:latest'
                }
            }
        }

        stage('Deploy to Kubernetes') {
            steps {
                sh 'kubectl apply -f kubernetes/'
            }
        }
    }
}
