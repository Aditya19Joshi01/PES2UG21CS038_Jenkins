pipeline {
    agent any
    stages {
        stage('Clone repository') {
            steps {
                checkout([$class: 'GitSCM',
                          branches: [[name: '*/main']],
                          userRemoteConfigs: [[url: 'https://github.com/Aditya19Joshi01/PES2UG21CS038_Jenkins.git']])
            }
        }
        stage('Build') {
            steps {
                build 'PES2UG21CS038-1'
                sh 'g++ main.cpp -o output'
            }
        }
        sta('Test') {
            steps {
                sh './output'
            }
        }
        stage('Deploy') {
            steps {
                echo 'deploy'
            }
        }
    }
    post {
        failure {
            error 'Pipeline failed'
        }
    }
}
