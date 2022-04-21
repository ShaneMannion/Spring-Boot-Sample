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
        stage('deploy') {
            steps {
                sh 'pwd'
            }
            steps {
                sh 'ls -lrt'
            }            
            steps {
                sh 'mvn springboot:run'
            }
        }
    }
}