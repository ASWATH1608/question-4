pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                echo 'Checking out source code...'
            }
        }

        stage('Show Build Info') {
            steps {
                echo "BUILD_NUMBER: ${env.BUILD_NUMBER}"
                echo "JOB_NAME: ${env.JOB_NAME}"
                echo "WORKSPACE: ${env.WORKSPACE}"
            }
        }

        stage('Run Linter') {
            steps {
                // Changed from 'sh' to 'bat' for Windows compatibility
                bat 'flake8 app.py'
            }
        }
    }
}
