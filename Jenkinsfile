pipeline {
    agent any
    
    stages {
        stage('Build') {
            steps {
                bat 'docker build -t myapp-image .'
            }
        }
        
        stage('Run Docker Container') {
            steps {
                bat 'docker run myapp-image'
            }
        }
    }
}
