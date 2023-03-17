pipeline {
    agent any
    environment {
        PROJECT_NAME = 'ABRA'
        OWNER_NAME   = 'KA-DA-B-RA'
    }

    stages {
        stage('BUILD-1') {
            steps {
                echo "Start stage-1"
                echo "Building project ${env.PROJECT_NAME}"
                echo "End of stage-1"
            }
        }
        stage('TEST-2') {
            steps {
                echo 'Start stage-2'
                echo 'Building ...'
                sh "cat /etc/passwd"
                echo 'End of stage-2'
            }
        }
        stage('DEPLOY-3') {
            steps {
                echo "Start stage-3 FOR owner ${env.OWNER_NAME}"
                sh '''
                    ls -la
                '''
                echo 'End of stage-3'
            }
        }    
    }
}
