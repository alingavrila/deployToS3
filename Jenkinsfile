@Library('demo-maven') _
    pipeline {
        agent any
        environment {
            AWS_CRED = 'deploytos3'
            bucketName = "mybucketname123321123"
            stackFileName = "cloudformation.yaml"
        }
        parameters {
            string(
                name: 'Stack Name',
                defaultValue: 'stack',
                description: 'The name of the stack',
            )
        }
        stages {
            stage('Upload template to S3') {                  
                steps {
                    script {
                        uploadToS3.upload(stackFileName: "$stackFileName", bucketName: "$bucketName")
                    }
                }
            }
            // stage('Deploy Stack') {                  
            //     steps {
            //         deployStack()
            //     }
            // }
        }
    }
