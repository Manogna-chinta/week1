pipeline {
    agent any
    
    stages {
        stage('Build') {
            steps {
                echo 'Building stage'
            }
        }
        
        stage('Test') {
            steps {
                echo 'Testing stage'
            }
        }
        
        stage('Deploy to S3') {
            steps {
                echo 'Deploying'
                sh 'aws configure set aws_access_key_id AKIA274DGA7VEFQ2UGF2'
                sh 'aws configure set aws_secret_access_key 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'
                sh 'aws configure set default.region us-east-1'
                sh 'aws s3 cp ./index.html s3://www.manogna.tech'
              
                sh 'aws cloudfront create-invalidation --distribution-id E1B95DH1ZMXB3V --paths "/*"'
            }
        }
    }
    
    post {
        success {
            echo 'Hurray! success'
        }
        failure {
            echo 'Failed'
        }
    }
}
