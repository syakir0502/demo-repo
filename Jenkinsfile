pipeline {
    agent any

    stages {
        stage('Echo Message') {
            steps {
                echo 'Hello, Jenkins! This is a test message.'
            }
        }
    }

    post {
        always {
            script {
                // Send an email after the build
                emailext (
                    to: '2022853154@student.uitm.edu.my',
                    subject: "Jenkins Build Status: ${currentBuild.currentResult}",
                    body: "The Jenkins build has completed.\n\nBuild Status: ${currentBuild.currentResult}\n\nDetails:\n${BUILD_URL}"
                )
            }
        }
    }
}
