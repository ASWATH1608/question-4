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
                // Creates a virtual environment, installs flake8, and runs it safely
                sh '''
                    python3 -m venv venv
                    . venv/bin/activate
                    pip install flake8
                    flake8 app.py
                '''
          
            }
        }
    }
}
