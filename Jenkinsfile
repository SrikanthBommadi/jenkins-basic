pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building the app...'
                sh 'javac MyApp.java'  // Example for Java
            }
        }

        stage('Test') {
            steps {
                echo 'Running tests...'
                sh 'java MyAppTest'  // Replace with real test command
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying the app...'
                sh './deploy.sh'  // A shell script for deployment
            }
        }
    }
}
