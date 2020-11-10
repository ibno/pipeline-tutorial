#!/bin/groovy
pipeline {

    agent none

    parameters {
        booleanParam(name: 'DEPLOY', defaultValue: false, description: 'Deploy?')
    }

    stages {
        stage('Build') {
            steps {
                echo 'Build'
            }
        }
    }
}