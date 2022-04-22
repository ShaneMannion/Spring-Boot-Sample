#!groovy
@Library("pipeline-library-sample") _
def demoLibrary = new com.yorku.DemoLibrary()

pipeline {
    agent { 
        node {
            label 'linux-node'
        }
    }
    stages {
        stage('build') {
            steps {
                demoLibrary.outputReport()
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