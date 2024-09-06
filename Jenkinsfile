pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                // Add your build steps here
                echo 'Building...'
            }
        }

        stage('Test') {
            steps {
                // Add your test steps here
                echo 'Running tests...'
            }
        }

        stage('Deploy') {
            steps {
                // Add your deployment steps here
                echo 'Deploying...'
            }
        }
    }

    post {
        always {
            emailext (
                subject: "Pipeline Status: ${currentBuild.result}",
                body: '''<html>
                    <body>
                        <p>Build Status: ${currentBuild.result}</p>
                        <p>Build Number: ${currentBuild.number}</p>
                        <p>Check the <a href="${env.BUILD_URL}">console output</a>.</p>
                    </body>
                </html>''',
                to: 'omnagare07@gmail.com',
                from: 'omnagare83@gmail.com',
                replyTo: 'omnagare07@gmail.com',
                mimeType: 'text/html'
            )
        }
    }
}
