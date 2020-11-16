pipeline {
    agent any

    stages {
        stage('Build Docker Image') {
            steps {
                echo 'Building Docker Image...'
                sh 'docker build . -t drcrinkle/nclouds-demo'
            }
        }
        stage('Push Docker Image to Dockerhub') {
            steps {
                echo 'Publishing Docker Image..'
                withDockerRegistry([ credentialsId: "41c3a71-8c0c-494b-b8ad-164e38cd252d", url: ""]){
                    sh 'docker push drcrinkle/nclouds-demo:latest'
                }
            }
        }
    }
}