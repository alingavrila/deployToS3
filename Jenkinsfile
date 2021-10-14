@Library('demo-maven') _
    pipeline {
        agent any
        environment {
            AWS_CRED = 'deploytos3',
            S3BUCKET = 'mybucketname123321123'
        }
        stages {
            stage('Upload template to S3') {                  
                steps {
                    script {
                        uploadToS3.upload()
                    }
                }
            }
            stage('Deploy Stack') {                  
                steps {
                    deployStack()
                }
            }
        }
    }
