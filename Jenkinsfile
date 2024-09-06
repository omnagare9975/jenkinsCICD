pipeline {
    agent any

    stages {
        stage('Checkout SCM') {
            steps {
                echo 'Checking out SCM...'
                // Add your SCM checkout step here
                // checkout scm
            }
        }

        stage('Build') {
            steps {
                echo 'Building...'
                // Add your build steps here
            }
        }

        stage('Test') {
            steps {
                echo 'Running tests...'
                // Add your test steps here
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying...'
                // Add your deployment steps here
            }
        }
    }

    post {
        always {
            script {
                // Debugging token values to check if they are accessible
                echo "Build Status: ${currentBuild.result}"
                echo "Build Number: ${currentBuild.number}"
                echo "Build URL: ${env.BUILD_URL}"
            }

            // Send email notification with build information
            emailext (
                subject: "Pipeline Status: ${BUILD_NUMBER}",
                body: '''<html>
                    <body>
                        <p>Build Status: ${BUILD_STATUS}</p>
                        <p>Build Number: ${BUILD_NUMBER}</p>
                        <p>Check the <a href="${BUILD_URL}">console output</a>.</p>
                    </body>
                </html>''',
                to: 'jaiswaladi246@gmail.com',
                from: 'jenkins@example.com',
                replyTo: 'jenkins@example.com',
                mimeType: 'text/html'
            )
        }
    }
}
