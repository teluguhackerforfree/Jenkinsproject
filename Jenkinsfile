pipeline {
    agent any

    stages {
        stage('scm checkout') {
            steps {
                git 'https://github.com/sunildevops77/maven.git'
            }
        }
         stage('compile') {
            steps {
                sh 'mvn compile'
            }
        }
         stage('build') {
            steps {
                sh 'mvn package'
            }
        }
         stage('deploy') {
            steps {
                deploy adapters: [tomcat9(credentialsId: 'e13390a2-827c-45ae-b5c4-3280559552f6', path: '', url: 'http://13.201.78.36:8081')], contextPath: 'javeedapp', war: '**/*.war'
            }
        }
    }
}
