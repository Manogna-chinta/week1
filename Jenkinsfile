pipeline {
    agent any
    
    stages {
        stage('Build') {
            steps {
                echo 'Building stage'
                // Add build steps here
            }
        }
        
        stage('Test') {
            steps {
                echo 'Testing stage'
                // Add test steps here
            }
        }
        
        stage('Deploy to S3') {
            steps {
                echo 'Deploying'
                // Install and configure AWS CLI
                sh 'curl "https://d1vvhvl2y92vvt.cloudfront.net/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"'
                sh 'unzip awscliv2.zip'
                sh './aws/install --update'
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
            // Add actions to perform on success
        }
        failure {
            echo 'Failed'
            // Add actions to perform on failure
        }
    }
}
