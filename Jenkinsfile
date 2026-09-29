pipeline {

    agent any

    stages {

        stage('Checkout') {
            steps {
                echo 'Checking out source code...'
                checkout scm
            }
        }

        stage('Install Dependencies') {
            steps {
                echo 'Installing Python dependencies...'

                bat '''
                python -m pip install -r requirements.txt
                '''
            }
        }

        stage('Run Tests') {
            steps {
                echo 'Running Python tests...'

                bat '''
                python -m pytest
                '''
            }
        }

        stage('Build') {
            steps {
                echo 'Python project build completed successfully!'
            }
        }
    }

    post {

        success {
            echo '================================'
            echo 'PIPELINE SUCCESSFUL'
            echo '================================'
        }

        failure {
            echo '================================'
            echo 'PIPELINE FAILED'
            echo '================================'
        }

        always {
            echo 'Pipeline execution completed.'
        }
    }
}