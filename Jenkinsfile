    pipeline {
    agent {
        label 'agent'
    }
    options {
        timeout(time: 10, unit: 'SECONDS' )
    }
    stages {
        stage('Build') {
            steps {
                echo 'Building the application...'
                sh 'echo build'
                sh 'sleep 10'
            }
        }
        stage('Test') {
            steps {
                echo 'Running tests...'
                sh 'echo test'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying the application...'
                sh 'echo deploy'
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
