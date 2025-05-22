pipeline {
    agent any
    stages {
        stage('Build Docker Image') {
            steps {
                script {
                    docker.build('myapp-image')
                }
            }
        }
        stage('Run Docker Container') {
            steps {
                sh 'docker run --rm myapp-image'
            }
        }
    }
}
