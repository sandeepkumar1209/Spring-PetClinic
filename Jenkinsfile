// Declarative Pipeline
def VERSION = '1.0.0'

pipeline {
    agent none
    // tools {
    //     maven 'apache-maven-3.6.3'
    // }
    environment {
        PROJECT = "WELCOME TO Jenkins Class"
        AZ_SUB_ID = "9ce91e05-4b9e-4a42-95c1-4385c54920c6"
        AZ_TEN_ID = "2b387c91-acd6-4c88-a6aa-c92a96cab8b1"
    }
    stages {
        stage("Dev Tools Verification") {
            when {
                branch 'development'
            }
            agent { label 'DEV' }
            steps {
                sh "mvn --version"
                sh "java -version"
                sh "terraform version"
                sh "packer version"
                sh "trivy --version"
                sh "trivy --version"
            }
        }

        //-----------------------------PRODUCTION---------------
        stage("PROD Tools Verification") {
            when {
                branch 'production'
            }
            agent { label 'PROD' }
            steps {
                sh "mvn --version"
                sh "java -version"
                sh "terraform version"
                sh "packer version"
            }
        }
    }
}
