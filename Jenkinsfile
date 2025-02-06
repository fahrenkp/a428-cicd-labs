pipeline {
    agent {
        docker {
            image 'node:16-buster-slim'
            args '-p 3000:3000'
        }
    }
    stages {
        stage('Checkout') {
            steps {
                sh 'rm -rf a428-cicd-labs'
                sh 'git clone -b react-app https://github.com/fahrenkp/a428-cicd-labs.git'
            }
        }
        stage('Build') {
            steps {
                dir('a428-cicd-labs') { // Masuk ke folder hasil clone
                    sh 'npm install'
                }
            }
        }
        stage('Test') { 
            steps {
                dir('a428-cicd-labs') { // Masuk ke folder hasil clone
                    sh './jenkins/scripts/test.sh' 
                }
            }
        }
    }
}
