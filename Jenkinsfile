#!groovy
@Library("pipeline-library-sample") _
def demoLibrary = new com.yorku.DemoLibrary()

pipeline {
    agent { 
        node {
            label 'linux-node'
        }
    }
    parameters {
        booleanParam(name: 'SAVE_JAR',
            defaultValue: true,
            description: 'Checkbox parameter')
    }    
    stages {
        stage('build') {
            steps {
                sh 'mvn clean install'
            }
        }
        stage('check workspace details') {
            steps {
                sh 'pwd && ls -lrt'
            }
        }  
        stage('copy latest jar'){
            when{
                expression { SAVE_JAR == true }
            }            
            steps {
                sh 'mkdir -p ~/jars && cp ./target/*.jar ~/jars'
            }
        }
    }
    post {
        always {
            script{ 
                demoLibrary.outputReport()
            }
        }
        success {
            echo 'Job completed successfully'
        }
        failure {
            echo 'Job failed'
        }
    }
}