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
                script {
                    def dockerComposeCmd = "docker-compose -f docker-compose.yml up --detach"
                    sshagent(['ec2-user-key']) {
                        sh "scp docker-compose.yml ec2-user@35.77.188.193:/home/ec2-user"
                        sh "ssh -o SrtictHostKeyChecking=no ec2-user@35.77.188.193 ${dockerComposeCmd}"
                }
            }
        }    
    }
}
}
