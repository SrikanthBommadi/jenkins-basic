pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building the application...'
                sh 'make build'
            }
        }

        stage('Test') {
            steps {
                echo 'Running tests...'
                sh 'make test'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying the application...'
                sh 'make deploy'
            }
        }
    }
}
