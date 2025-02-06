pipeline {
    agent {
        docker {
            image 'node:16-buster-slim' 
            args '-p 3000:3000' 
        }
    }
    stage('Build') {
        steps {
            dir('a428-cicd-labs') {
                sh 'npm install'
            }
        }
    }   
}
//Scripct Yang Bisa dibuild

// pipeline {
//     agent any
//     stages {
//         stage('Checkout') {
//             steps {
//                 sh 'rm -rf a428-cicd-labs'
//                 sh 'git clone -b react-app https://github.com/fahrenkp/a428-cicd-labs.git'
//             }
//         }
//     }
// }
