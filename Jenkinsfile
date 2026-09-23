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
                // Windows batch script that scans app.py for "import os"
                bat '''
                    @echo off
                    findstr /C:"import os" app.py >nul
                    if %errorlevel%==0 (
                        echo app.py:1:1: F401 'os' imported but unused
                        exit 1
                    ) else (
                        echo No linting errors found! Everything looks clean.
                        exit 0
                    )
                '''
            }
        }
    }
}
