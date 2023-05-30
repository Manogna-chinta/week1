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
