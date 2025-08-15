pipeline {
    agent   {
        label 'AGENT-1' 
    }
    environment {
        COURSE = "jenkins"
    }

    // Build
    stages {
        stage('Build') {
            steps {
                script{ //this 3 scripts added at 3rd time
                    //echo 'Building..'
                    sh """
                        echo "Hello Build"
                        env
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