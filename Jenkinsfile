pipeline {
    agent any

    stages {
        stage('Checkout SCM') {
            steps {
                echo 'Checking out SCM...'
                // You can add your actual SCM checkout step here
                // checkout scm
            }
        }

        stage('Build') {
            steps {
                echo 'Building...'
                // Add your actual build steps here
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
            // Debugging tokens before using them in the email
            script {
                echo "Build Status: ${currentBuild.result}"
                echo "Build Number: ${currentBuild.number}"
                echo "Build URL: ${env.BUILD_URL}"
            }

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
                from: 'jenkins@example.com',
                replyTo: 'jenkins@example.com',
                mimeType: 'text/html'
            )
        }
    }
}
