pipeline {
    agent {
        docker {
            image 'maven:3.8.1-adoptopenjdk-11'
            args '-u root'
            reuseNode true
        }
    }

    stages {
        // Test stage
        stage('test') {
            steps {
                echo 'Hello World from Test stage'
            }
        }

        // Build stage
        stage('build') {
            steps {
                echo 'Installing Docker'
                withRun('-u root') {
                    sh '''
                    apk --no-cache add docker
                    rc-update add docker boot
                    service docker start
                    '''
                }
                echo 'Hello World from Build stage'
            }
        }

        // Deploy stage
        stage('deploy') {
            steps {
                echo 'Hello World from Deploy stage'
            }
        }
    }
}
