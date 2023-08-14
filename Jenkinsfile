pipeline {
    agent any

    stages {
        
        stage('Build') {
            environment {
            STACK_NAME = 'python-app'
            S3_BUCKET="demo-sam-app-s3-bucket"
                }
            steps {
                
                withAWS(credentials: 'sam-demo-test', region: 'ap-south-1') {
                sh 'sam build && sam deploy --stack-name $STACK_NAME -t template.yaml --s3-bucket $S3_BUCKET --capabilities CAPABILITY_IAM --no-confirm-changeset'
                
            }
          }
        }
        
        
    }
}

