

pipeline {
    agent {
        docker {
            image 'node:6-alpine'
        }
    }

    stages {
        stage('Build') {
            steps {
                sh 'npm install'
            }
        }
        stage('Test') {
            steps {
                sh 'npm test'
            }
        }
        stage('Deploiement Ansible') {
            steps {
                sh 'ls'
            }
        }
    }

}

