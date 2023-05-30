pipeline {
    agent any 
    options {
        cache('my-cache') {
            customWorkspace 'src'
            files 'pom.xml', 'src/**/*'
        }
    }
    stages {
        stage ('Build') {
            steps {
                echo "Building stage"
            }
        }
        stage ('Test') {
            steps {
                echo "Testing stage"
            }
        }
        stage ('Deploy to S3') {
            steps {
                echo "Deploying"
            }
        }
    }
    post {
        success {
            echo "Hurray! success"
        }
        failure {
            echo "failed"
        }
    }
}
