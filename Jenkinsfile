pipeline {
    agent {
        docker {
            image 'maven:3.8.1-adoptopenjdk-11'
            args '-u root'
            reuseNode true
            // Use a custom Dockerfile to run Docker inside Docker
            dockerfile '''
            FROM docker:latest
            RUN apk --no-cache add openrc docker-compose
            '''
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
                sh '''
                apk --no-cache add docker
                rc-update add docker boot
                service docker start
                '''
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
