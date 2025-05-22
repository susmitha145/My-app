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

    post {
        success {
            emailext subject: 'Jenkins Job Success: ${JOB_NAME} #${BUILD_NUMBER}',
                     body: "Good news! The Jenkins job '${JOB_NAME}' (build #${BUILD_NUMBER}) completed successfully.\n\nCheck it here: ${BUILD_URL}",
                     to: 'mksush17@gmail.com'
        }

        failure {
            emailext subject: 'Jenkins Job FAILED: ${JOB_NAME} #${BUILD_NUMBER}',
                     body: "Oops! The Jenkins job '${JOB_NAME}' (build #${BUILD_NUMBER}) failed.\n\nCheck it here: ${BUILD_URL}",
                     to: 'mksush17@gmail.com'
        }
    }
}
