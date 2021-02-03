pipeline {
    agent any 
    stages {
        stage('Clone Repo') { 
            steps {
          sh "export AWS_DEFAULT_REGION=us-east-1"
          sh "aws cloudformation create-stack --stack-name myteststack --template-body file://SimpleECS-Cluster-Service-TaskDefinition.yaml --region 'us-east-1'"          
         }
     }
  }
}


