pipeline {
    agent any
    parameters {
        gitParameter branchFilter: 'origin/(.*)', defaultValue: 'master', name: 'BRANCH', type: 'PT_BRANCH'
    }
    stages {
        stage('checkout') {
            steps {
                echo "pipeling running in checout"  
            }
        }
        stage('BranchValidation') {
            steps{
                echo "pipeling running in ${params.BRANCH}"
            }
        }
        stage('mvn-build') {
            steps {
                echo "creating archive using maven"
            }
        }
        stage('sonar-scanner') {
            steps {
                echo "static code analysis using sonar"
            }
        }
        stage('upload') {
            steps {
                script {
                    echo "upload artifacts using nexus"
                }
            }
        }
        stage('deploy'){
            steps{
                script{
                    echo "deploy archive using ansible"
                }
            }
        }
    }
}
