#!/bin/groovy
pipeline {

    agent none

    parameters {
        booleanParam(name: 'DEPLOY', defaultValue: false, description: 'Deploy?')
        string(name: 'VERSION', defaultValue: 'latest', description: 'Version to build')
    }

    stages {
        stage('Build') {
            steps {
                mvn clean install
            }
        }
    }
}