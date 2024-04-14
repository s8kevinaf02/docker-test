pipeline {
    agent {
        docker {
            image 'maven:3.8.1-adoptopenjdk-11'
            args '-u root'
            reuseNode true
            privileged true
            services docker: 'docker:dind'
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
                apt-get update
                apt-get install -y apt-transport-https ca-certificates curl software-properties-common
                curl -fsSL https://download.docker.com/linux/ubuntu/gpg | apt-key add -
                add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"
                apt-get update
                apt-get install -y docker-ce
                usermod -aG docker jenkins
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
