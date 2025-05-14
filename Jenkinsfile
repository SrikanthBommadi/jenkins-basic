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
    post {
        always {
            echo " always show this "
            deleteDir() //it will delete the data of build which is in workspace 
        }
        success {
            echo "when it success"
        }
        failure {
            echo "when it failure"
        }
    }
}
