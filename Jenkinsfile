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
                // Printing the specific environment variables requested
                echo "BUILD_NUMBER: ${env.BUILD_NUMBER}"
                echo "JOB_NAME: ${env.JOB_NAME}"
                echo "WORKSPACE: ${env.WORKSPACE}"
            }
        }

        stage('Run Linter') {
            steps {
                // Runs flake8 on the app.py file
                sh 'flake8 app.py'
            }
        }
    }
}
