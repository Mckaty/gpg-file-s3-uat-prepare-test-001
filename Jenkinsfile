pipeline {
    agent any

    stages {
        stage('Prepare GPG UAT Test') {
            steps {
                aws s3 mv s3://poc-gpg-bucket-uat-142603072023/archive/ s3://poc-gpg-bucket-uat-142603072023/in/ --recursive --exclude "*" --include "*.pgp"
            }
        }

        stage('List S3 Outbox') {
            steps {
                sh 'aws s3 ls s3://poc-gpg-bucket-uat-142603072023/in/ '
            }
        }

        stage('List S3 Inbox') {
            steps {
                sh 'aws s3 ls s3://poc-gpg-bucket-uat-142603072023/out/ '
            }
        }

        stage('List S3 Archive') {
            steps {
                sh 'aws s3 ls s3://poc-gpg-bucket-uat-142603072023/archive/ '
            }
        }
    }
}    
