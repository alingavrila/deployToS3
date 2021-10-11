@Library('demo-maven') _
    pipeline {
        agent any
        environment {
            AWS_CRED = 'deploytos3'
        }
        stages {
            stage('Upload template to S3') {                  
                steps {
                    uploadToS3.upload()
                }
            }
            stage('Deploy EC2') {                  
                steps {
                    deployEC2()
                }
            }
        }
    }
