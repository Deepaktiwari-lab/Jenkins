pipeline {
    agent any
    tools {
        go '1.19'
    }
    environment {
        GO111MODULE='on'
    }

    stages {
        stage('Test') {
            steps {
                git 'https://github.com/kodekloudhub/go-webapp-sample.git'
                sh 'go test ./...'
            }
        }
        stage('Build') {
            steps { 
                 git 'https://github.com/kodekloudhub/go-webapp-sample.git'
                 sh 'go build .'
                 sh './go-webapp-sample'
                 
            }   
        }
        stage('Run') {
            steps {
                sh 'cd /var/lib/jenkins/workspace/go-full-pipeline && go-webapp-sample &'
            }
        }   
    }
}