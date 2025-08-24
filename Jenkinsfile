pipeline {
    agent any

    stages {
        stage('Build & Tag Docker Image') {
            steps {
                script {
                    withDockerRegistry(credentialsId: 'dockerhub', toolName: 'dockerhub') {
                        sh "docker build -t vishal431/adservice:latest ."
                    }
                }
            }
        }
        
        stage('Push Docker Image') {
            steps {
                script {
                    withDockerRegistry(credentialsId: 'dockerhub', toolName: 'dockerhub') {
                        sh "docker push vishal431/adservice:latest "
                    }
                }
            }
        }
    }
}
