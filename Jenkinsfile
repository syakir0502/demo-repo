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
                    to: 'your-email@example.com',
                    subject: "Jenkins Build Status: ${currentBuild.currentResult}",
                    body: "The Jenkins build has completed.\n\nBuild Status: ${currentBuild.currentResult}\n\nDetails:\n${BUILD_URL}"
                )
            }
        }
    }
}
