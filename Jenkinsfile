pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building stage'
                // Cache the artifacts using Job Cacher Plugin
                jobCacher(cacheName: 'my-cache') {
                    // Define the steps for the build
                    // ...
                }
            }
        }
        stage('Test') {
            steps {
                echo 'Testing stage'
                // Restore the cached artifacts using Job Cacher Plugin
                jobCacher(cacheName: 'my-cache', restore: true) {
                    // Define the steps for testing
                    // ...
                }
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
