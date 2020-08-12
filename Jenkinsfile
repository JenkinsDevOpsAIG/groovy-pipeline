#!/usr/bin/env groovy
// Jenkinsfile (Declarative Pipeline)
pipeline {
    agent any
    
    stages {
        stage(checkout){
            steps {
                checkout([$class: 'GitSCM', branches: [[name: '*/master']], 
                      doGenerateSubmoduleConfigurations: false, 
                      extensions: [], 
                      submoduleCfg: [], 
                      userRemoteConfigs: [[url: 'https://github.com/JenkinsDevOpsAIG/groovy-pipeline.git']]])
            }
        }
        stage('clone repo and clean') {
            steps {
                bat "del /s groovy-pipeline"
                bat "git clone https://github.com/JenkinsDevOpsAIG/groovy-pipeline.git"
                //bat "mvn clean -f groovy-pipeline"
                echo 'cloned repo..Done'
            }
        }
        stage('Test') {
            steps {
                //bat "mvn test -f groovy-pipeline"
                
                echo 'Testing..Done'
            }
        }
        stage('Deploy') {
            steps {
                //bat "mvn deploy -f groovy-pipeline"
                echo 'Deploying....Done'
            }
        }
    }
}
