pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building stage'
                cache(key: 'my-cache', paths: ['pom.xml', 'src/**/*'])
            }
        }
        stage('Test') {
            steps {
                echo 'Testing stage'
                unstash 'my-cache'
            }
        }
        stage('Deploy to S3') {
            steps {
                echo 'Deploying'
            }
        }
    }

    post {
        success {
            echo 'Hurray! success'
        }
        failure {
            echo 'failed'
        }
    }
}
