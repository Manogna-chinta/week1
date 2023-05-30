pipeline {
    agent any

    stages {
        stage ('Build') {
            steps {
                echo 'Building stage'
                jobCacher(cacheName: 'my-cache') {
                    // Add build steps here
                    // ...
                }
            }
        }
        
        stage ('Test') {
            steps {
                echo 'Testing stage'
                jobCacher(cacheName: 'my-cache', restore: true) {
                    // Add test steps here
                    // ...
                }
            }
        }

        stage ('Deploy to S3') {
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
            echo 'Failed'
            currentBuild.result = 'FAILURE'
        }
    }
}
