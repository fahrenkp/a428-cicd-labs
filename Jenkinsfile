pipeline {
    agent {
        docker {
            image 'node:16-buster'
            args '-p 3000:3000'
        }
    }
    stages {
        stage('Checkout') {
            steps {
                sh 'rm -rf a428-cicd-labs'
                sh 'git clone -b react-app https://github.com/fahrenkp/a428-cicd-labs.git'
                sh 'ls -la a428-cicd-labs'
            }
        }
        stage('Build') {
            steps {
                dir('a428-cicd-labs') {
                    sh 'npm install'
                }
            }
        }
        stage('Test') { 
            steps {
                dir('a428-cicd-labs') {  
                    sh 'chmod +x ./jenkins/scripts/test.sh'
                    sh './jenkins/scripts/test.sh' 
                }
            }
        }
    }
}
