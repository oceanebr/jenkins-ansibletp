

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
        stage('Install ansible') {
            steps {
                sh 'apk add ansible'
                sh 'apk add python3'
                sh "ansible --version"
                sh " ansible-playbook -i inventaire.ini playbook.yml "
            }
        }
    }

}

