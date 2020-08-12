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
                bat "pwd"
                bat "del C:\Program Files (x86)\Jenkins\workspace\GroovySampleJob\groovy-pipeline"
                bat "git clone https://github.com/JenkinsDevOpsAIG/groovy-pipeline.git"
                //bat "mvn clean -f groovy-pipeline"
                echo 'cloned repo..Done'
            }
        }
        stage('Test') {
            steps {
                //bat "mvn test -f groovy-pipeline"
                bat "git status https://github.com/JenkinsDevOpsAIG/groovy-pipeline.git"
                
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
