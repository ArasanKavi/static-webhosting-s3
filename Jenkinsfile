pipeline {
    agent any
    stages {
        stage('deploy') {
            steps {
              sh "aws configure set region $AWS_DEFAULT_REGION" 
              sh "aws configure set aws_access_key_id $AWS_ACCESS_KEY_ID"  
              sh "aws configure set aws_secret_access_key $AWS_SECRET_ACCESS_KEY"
              sh "aws s3 cp . Code/ s3://bucketnewly --recursive"
              sh "aws cloudfront create-invalidation --distribution-id E3N569NDVQ6CD8 --paths '/*'"
            }
        }
    }
}
