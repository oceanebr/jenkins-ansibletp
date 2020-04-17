node{
 stage('Clone'){
     git :'https://github.com/oceanebr/jenkins-ansibletp.git'
 }
 stage('Installation') {
     sh 'apk add --update nodejs nodejs-npm'
     sh 'npm i'
 }
  stage('Test') {
     sh 'npm test'
 }

 stage('Ansible') {
     sh 'ansible-playbook -i inventaire.ini playbook.yml'
 }
}

// pipeline {
//     agent {
//         docker {
//             image 'node:6-alpine'
//         }
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
// // Demande l'aaccord pour passer a l'étape suivante
//         // stage('Deliver') {
//         //     steps {
//         //         input message: 'Pret a delivrer l application ?'
//         //     }
//         // }

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


