#!/bin/groovy
pipeline {

    agent none

    parameters {
        booleanValue(name: 'DEPLOY', defaultValue: false, description: 'Deploy?')
    }

    stages {
        stage('Build') {
            steps {
                echo 'Build'
            }
        }
    }
}