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
                sh 'mvn springboot:run'
            }
        }
    }
}