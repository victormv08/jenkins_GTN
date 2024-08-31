pipeline {
    agent any
    stages {
        stage('Clone repository') {
            steps {
                git 'https://github.com/victormv08/jenkins_GTN.git'
            }
        }
        stage('Build Docker Image') {
            steps {
                script {
                    dockerImage = docker.build("AppGithub")
                }
            }
        }
        stage('Deploy') {
            steps {
                script {
                    dockerImage.run('-d -p 80:80 AppGithub')
                }
            }
        }
    }
}
