pipeline {
    agent any

    stages {
        
        stage('Build') {
            environment {
            STACK_NAME = 'sam-app'
            S3_BUCKET = 'sam-jenkins-demo-user1'
            }
            steps {
                dir('Python-app'){
                withAWS(credentials: 'sam-demo-test', region: 'ap-south-1') {
                sh 'sam build && sam deploy --stack-name $STACK_NAME --s3-bucket $S3_BUCKET --capabilities CAPABILITY_IAM --no-confirm-changeset'
                }
            }
          }
        }
        
        
    }
}

