pipeline {
    agent any

    stages {
        stage('Build & Tag Docker Image') {
            steps {
                script {
                    withDockerRegistry(credentialsId: 'dockerhub', toolName: 'dockerhub') {
                        sh "docker build -t vishal431/checkoutservice:latest ."
                    }
                }
            }
        }
        
        stage('Push Docker Image') {
            steps {
                script {
                    withDockerRegistry(credentialsId: 'dockerhub', toolName: 'dockerhub') {
                        sh "docker push vishal431/checkoutservice:latest "
                    }
                }
            }
        }
    }
}
