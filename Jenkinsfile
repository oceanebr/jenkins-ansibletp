

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
                sh ' echo "192.168.1.27   jenkins" >> /etc/hosts'
                sh 'cat /etc/hosts'
                sh " ansible-playbook -i inventaire.ini playbook.yml "
            }
        }
    }

}

