pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Clones your repository code
                checkout scm
            }
        }

        stage('Show Build Info') {
            steps {
                // Prints the requested Jenkins environment variables
                echo "Build Number: ${env.BUILD_NUMBER}"
                echo "Job Name: ${env.JOB_NAME}"
                echo "Workspace Path: ${env.WORKSPACE}"
            }
        }

        stage('Run Linter') {
            steps {
                // Installs flake8 and runs it on app.py
                sh 'pip install flake8'
                sh 'flake8 app.py'
            }
        }
    }
}
