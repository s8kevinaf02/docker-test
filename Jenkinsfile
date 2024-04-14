pipeline {
    agent {
        docker{
            image 'maven:3.8.1-adoptopenjdk-11'
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
