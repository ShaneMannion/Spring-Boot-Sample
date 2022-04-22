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
    }
}