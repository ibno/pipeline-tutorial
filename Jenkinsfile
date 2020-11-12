#!/bin/groovy
pipeline {

    agent any

    parameters {
        booleanParam(name: 'DEPLOY', defaultValue: false, description: 'Deploy?')
        string(name: 'VERSION', defaultValue: 'latest', description: 'Version to build')
        booleanParam(name: "MAKE_RELEASE", defaultValue: false, description: "Release and tag")
    }

    stages {
        stage('Build') {
            steps {
                echo "Build"
                script {
                    files = findFiles(glob: "**/a/build/*.yaml")
                    for (file in files) {
                        print file.getPath()
                    }
                    print files
                }
            }
        }
        stage('Release') {
            when {
                expression: params.MAKE_RELEASE
            }
            steps {
                sh 'mvn gitflow:release'
            }
        }
    }
}