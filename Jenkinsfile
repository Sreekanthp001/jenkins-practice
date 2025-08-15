pipeline {
    agent   {
        label 'AGENT-1' 
    }
    environment { // this one and 15th to 18th line added 4th time
        COURSE = "jenkins"
    }
    options {//this one 5th added
        timeout(time: 30, unit: 'MINUTES')
        disableConcurrentBuilds()
    }
    parameters { //this one added 6th and 30 also
        string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')
        text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')
        booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value')
        choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')
        password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
    }

    // Build
    stages {
        stage('Build') {
            steps {
                script{ //this 3 scripts added at 3rd time
                    //echo 'Building..'
                    sh """
                        echo "Hello Build"
                        sleep 10
                        env
                        echo "Hello ${params.PASSWORD}"
                    """
                }                
            }
        }
        stage('Test') {
            steps {
                script{
                    echo 'Testing..'
                }
            }
        }
        stage('Deploy') {
            steps {
                script{
                    echo 'Deploying....'
                }
            }
        }
        
    }

    post { //this is added 2nd 
        always {
            echo 'I will always say Hello again!'
            deleteDir()
        }
        success {
            echo 'Hello Success'
        }
        failure {
            echo 'Hello Failure'
        }
    }
}