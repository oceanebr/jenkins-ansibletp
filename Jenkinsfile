node{
 stage('Clone'){
     git :'https://github.com/oceanebr/jenkins-ansibletp.git'
 }
 stage('Ansible') {
     sh 'ansible-playbook -i inventaire.ini playbook.yml'
 }
}


//     environment {
//     CI = 'true'
//     }

//     stages {
//         stage('Build') {
//             steps {
//                 sh 'npm install'
//             }
//         }

//         stage('Test') {
//             steps {
//                 sh 'npm test'
//             }
//         }

//         stage('Deliver') {
//             steps {
//                 input message: 'Pret a delivrer l application ?'
//             }
//         }

//         stage('Ansible installation'){
//             steps {
//                 script {
//                     sh 'apk add ansible'
//                 }

//                 script {
//                     sh 'apk add python3'
//                 }
//             }
//         }

//         stage('Ansible init') {
//             steps {
//                 script {
//                     sh 'ansible --version'
//                 }
//             }
//         }

//         stage(' Ansible - test') {
//             steps {
//                 dir('dev/ansible'){
//                     sh 'ansible all -m ping'
//                 }
//             }
//         }

//         stage('Deploiement Ansible') {
//             steps {
//                 ansiblePlaybook (
//                     playbook: 'playbook.yml'
//                 )
//             }
//         }
//     }
// }



// pipeline {
//     agent {
//         docker {
//             image 'node:6-alpine'
//         }
//     }

//         stages {
//     //     stage('Build') {
//     //         steps {
//     //             sh 'npm install'
//     //         }
//     //     }
//         stage('Test') {
//             steps {
//                 sh 'apk update'
//                 sh 'apk add openssh'
//                 sh 'ssh-keygen -t rsa -N " "'
//             }
//         }

//     //     stage ('Config ssh') {
//     //         steps{
//     //             sshagent(credentials : ['use-the-id-from-credential-generated-by-jenkins']) {
//     //                 sh 'ssh -o StrictHostKeyChecking=no user-ansible@jenkins uptime'
//     //                 sh 'ssh -v user-ansible@jenkins'
//     //                 sh 'scp ./source/filename user-ansible@jenkins:/remotehost/target'
//     //             }
//     //         }
//     //     }
//             stage('Install ansible') {
//                 steps {
//                     sh 'apk add ansible'
//                     sh 'apk add python3'
//                     sh 'ssh -tt user-ansible@192.168.1.27'
//                     // sh ' echo "192.168.1.27   jenkins" >> /etc/hosts'
//                     // sh 'cat /etc/hosts'
//                     sh " ansible-playbook -i inventaire.ini playbook.yml "
//                 }
//             }
//         }

// }

