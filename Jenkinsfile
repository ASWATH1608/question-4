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
                // Using 'bat' for Windows, creating a local virtual environment, 
                // installing flake8 locally, and running it on app.py
                bat '''
                    python -m venv venv
                    call venv\\Scripts\\activate
                    pip install flake8
                    flake8 app.py
                '''
            }
        }
    }
}
