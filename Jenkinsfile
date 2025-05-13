pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building the application...'
                // Example build command
                sh '  mkdir build'
            }
        }

        stage('Test') {
            steps {
                echo 'Running tests...'
                // Example test command
                sh 'mkdir test'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying the application...'
                // Example deploy command
                sh 'mkdir deploy'
            }
        }
    }
}
