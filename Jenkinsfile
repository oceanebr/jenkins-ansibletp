

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
                sh 'apk update'
                sh 'apk add openssh'
            }
        }

        // stage ('Config ssh') {
        //     steps{
        //         sshagent(credentials : ['use-the-id-from-credential-generated-by-jenkins']) {
        //             sh 'ssh -o StrictHostKeyChecking=no user-ansible@jenkins uptime'
        //             sh 'ssh -v user-ansible@jenkins'
        //             sh 'scp ./source/filename user-ansible@jenkins:/remotehost/target'
        //         }
        //     }
        // }
        stage('Install ansible') {
            steps {
                sh 'apk add ansible'
                sh 'apk add python3'
                sh "ansible --version"
                // sh ' echo "192.168.1.27   jenkins" >> /etc/hosts'
                // sh 'cat /etc/hosts'
                sh " ansible-playbook -i inventaire.ini playbook.yml "
            }
        }
    }

}

