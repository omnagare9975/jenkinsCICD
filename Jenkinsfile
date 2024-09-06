pipeline {
    agent any

    stages {
        stage("Checkout") {
            steps {
                git branch: 'dev', url: 'https://github.com/omnagare9975/jenkinsCICD.git'
            }
        }
        stage("Building") {
            steps {
                sh 'echo "Building The File"'
            }
        }
        stage("Test") {
            steps {
                sh 'echo "Testing the File"'
            }
        }
        stage("Deploying Application") {
            steps {
                sh 'echo "This is Tested"'
            }
        }
    }

    post {
        failure {
            mail to: 'omnagare07@gmail.com',
                subject: "Build Failed: ${env.JOB_NAME} ${env.BUILD_NUMBER}",
                body: "Something went wrong in the build pipeline."
        }
    }
}
