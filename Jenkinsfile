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
                    environmentDashboard {
                        environmentName('Environment-1')
                        componentName('WebApp-1')
                        buildNumber('Version-1')
                    }
            }
        }
        stage('Release') {
            when {
                expression {
                    params.MAKE_RELEASE
                }
            }
            steps {

                sh 'mvn gitflow:release'
            }
        }
    }
}