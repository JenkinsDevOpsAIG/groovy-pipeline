#!/usr/bin/env groovy
// Jenkinsfile (Declarative Pipeline)
pipeline {
    agent any

    stages {
        stage('clone repo and clean') {
            steps {
                bat "git clone https://github.com/JenkinsDevOpsAIG/groovy-pipeline.git"
                bat "mvn clean -f groovy-pipeline"
                echo 'cloned repo..Done'
            }
        }
        stage('Test') {
            steps {
                bat "mvn test -f groovy-pipeline"
                
                echo 'Testing..Done'
            }
        }
        stage('Deploy') {
            steps {
                bat "mvn deploy -f groovy-pipeline"
                echo 'Deploying....Done'
            }
        }
    }
}
