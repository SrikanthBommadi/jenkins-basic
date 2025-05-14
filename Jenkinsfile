    pipeline {
    agent {
        label 'agent'
    }
    options {
        timeout(time: 10, unit: 'SECONDS' ) //this for time out after soem time 
        disableConcurrentBuilds()           // 1 build is running if you press 2nd build it will wait until 1st build done
        retry(2)                            // if it fails once it will start again two as we mention
    }
    stages {
        stage('Build') {
            steps {
                echo 'Building the application...'
                sh 'echo build'
                sh 'sleep 2'
                error 'pipe failed'
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
