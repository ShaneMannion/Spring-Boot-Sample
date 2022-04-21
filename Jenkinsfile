pipeline {
    agent { 
        node {
            label 'linux-node'
        }
    }
    stages {
        stage('build') {
            steps {
                sh 'mvn clean install'
            }
        }
        stage('checks') {
            steps {
                sh 'ls -lrt && pwd'
            }
        }        
        stage('deploy') {
            steps {
                sh 'mvn spring-boot:run'
            }
        }
        stage('test') {
            steps {
                sh 'curl http://localhost:8090'
            }
        }
    }
}