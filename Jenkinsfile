pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Starting Build'
                bat 'if not exist build mkdir build'
                bat 'echo Build Successful > build\\output.txt'
            }
        }

        stage('Test') {
            steps {
                echo 'Starting Test'
                bat 'if exist build\\output.txt (echo TEST PASSED) else (exit /b 1)'
            }
        }
    }

    post {
        success {
            echo 'BUILD AND TEST SUCCESSFUL!'
        }
        failure {
            echo 'BUILD OR TEST FAILED!'
        }
        always {
            echo 'Pipeline execution completed.'
        }
    }
}