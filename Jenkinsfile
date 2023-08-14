pipeline {
    agent any

    stages {
        
        stage('Build') {
            environment {
            STACK_NAME = 'python-app'
                }
            steps {
                dir('Python-app'){
                withAWS(credentials: 'sam-demo-test', region: 'ap-south-1') {
                sh 'sam build && sam deploy --stack-name $STACK_NAME --capabilities CAPABILITY_IAM --no-confirm-changeset'
                }
            }
          }
        }
        
        
    }
}

