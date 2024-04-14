pipeline {
    agent {
        docker {
            image 'docker:latest'
            args '-u root'
            privileged true
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
