pipeline {
    agent any

    stages {
        stage('Build & Tag Docker Image') {
            steps {
                script {
                    dir('src') {

                    withDockerRegistry(credentialsId: 'dockerhub', toolName: 'dockerhub') {
                        sh "docker build -t vishal431/cartservice:latest ."
                    }
                        }
                }
            }
        }
        
        stage('Push Docker Image') {
            steps {
                script {
                    withDockerRegistry(credentialsId: 'dockerhub', toolName: 'dockerhub') {
                        sh "docker push vishal431/cartservice:latest "
                    }
                }
            }
        }
    }
}
