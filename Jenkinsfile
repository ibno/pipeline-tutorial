#!/bin/groovy
pipeline {

    agent any

//    parameters {
//        booleanParam(name: 'DEPLOY', defaultValue: false, description: 'Deploy?')
//        string(name: 'VERSION', defaultValue: 'latest', description: 'Version to build')
//    }

    stages {
        stage('Build') {
            steps {
                echo "Build"
                script {
                    files = findFiles(glob: "**/*.yaml")
                }
            }
        }
    }
}