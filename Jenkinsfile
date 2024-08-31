pipeline {
    agent any
    stages {
        stage('Clone repository') {
            steps {
                git 'https://github.com/marialu11/Jenkins_GTN.git'
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
