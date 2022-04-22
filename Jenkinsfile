#!groovy
@Library('pipeline-library-sample')
import com.yorku.DemoLibrary
def demoLibrary = new DemoLibrary()

pipeline {
    agent { 
        node {
            label 'linux-node'
        }
    }
    stages {
        stage('build') {
            steps {
                demoLibrary.outputReport
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