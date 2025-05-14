    pipeline {
    agent {
        label 'srikanth'
    }
    parameters { // we can store configuration here 
        string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')
        text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')
        booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value')
        choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')
        password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
    }
    options {
        timeout(time: 30, unit: 'SECONDS' ) //this for time out after soem time. 
        disableConcurrentBuilds()           // 1 build is running if you press 2nd build it will wait until 1st build done
        retry(2)                            // if it fails once it will start again two as we mention
    }
    stages {
        stage('Build') {
            steps {
                echo 'Building the application...'
                sh 'echo build'
                sh 'sleep 2'
                //error 'pipe failed'
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
        stage ('parameter') {
            steps {
                 echo "Hello ${params.PERSON}"
                echo "Biography: ${params.BIOGRAPHY}"
                echo "Toggle: ${params.TOGGLE}"
                echo "Choice: ${params.CHOICE}"
                echo "Password: ${params.PASSWORD}"
            }
        }
         stage('input') {
            input {
                message "Should we continue?"
                ok "Yes, we should."
                submitter "alice,bob"
                parameters {
                    string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')
                }
            }
            steps {
                echo "Hello, ${PERSON}, nice to meet you."
            }
        }
        stage('when') {
            when {
                branch 'production'
            }
            steps {
                sh " it is Deploying "
            }
        }
    }
    post {
        always {
            echo " always show this "
            deleteDir() //it will delete the data of build which is in workspace 
        }
        success {
            echo " when it success "
        }
        failure {
            echo " when it failure "
        }
    }
}
