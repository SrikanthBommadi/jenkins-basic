pipeline {
    agent {
        label 'agent'
    }
    stages {
        stage('Build') {
            steps {
                echo 'Building the application...'
                sh 'mkdir build'
            }
        }
        stage('Test') {
            steps {
                echo 'Running tests...'
                sh 'mkdir test'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying the application...'
                sh 'mkdir deploy'
            }
        }
    }
}
