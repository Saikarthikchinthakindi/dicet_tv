pipeline {
    agent any

    stages {
        stage('code from github') {
            steps {
                git 'https://github.com/BHUPESHGCTECH/dicet_tv.git'
            }
        }
        stage('Build the code') {
            steps {
                sh 'mvn clean package'
            }
        }
        stage('deploy') {
            steps {
                deploy adapters: [tomcat9(credentialsId: 'tomcat1', path: '', url: 'http://54.248.13.181:8081/')], contextPath: 'raju', war: '**/*.war'
            }
        }
    }
}
