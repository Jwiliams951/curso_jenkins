pipeline {
    agent any

    parameters {
        string(name: 'BRANCH', defaultValue: 'main', description: 'Branch name')
    }

    stages {
        stage('Step1') {
            steps {
                echo 'step 1'
                sh 'printenv'
            }
        }
        stage('Step2') {
            when {
                expression { params.BRANCH ==~ /(main|Hotfix)/ }
            }
            steps {
                echo 'step 2'
            }
        }
        stage('Step3') {
            when {
                expression { params.BRANCH ==~ /(Release)/ }
            }
            steps {
                echo 'step 3'
            }
        }
    }
}
