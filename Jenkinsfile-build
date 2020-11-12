#!/bin/groovy
pipeline {

    agent {
        docker {
            image 'maven:3-alpine'
            args '-v $HOME/.m2:/root/.m2'
        }
    }

    parameters {
        booleanParam(name: 'DEPLOY', defaultValue: false, description: 'Deploy?')
        string(name: 'VERSION', defaultValue: 'latest', description: 'Version to build')
    }

    stages {
        stage('Build') {
            steps {
                sh 'mvn clean install'
            }
        }
    }
}