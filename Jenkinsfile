pipeline {
    agent any
    stages {
        stage('Lint HTML') {
            steps {
                sh 'tidy -q -e *.html'
            }
        }
        stage('Upload to AWS') {
            steps {
                withAWS(region:'us-east-2', credentials:'ac14e4b7-d2d3-4606-81b0-7e65c16e8707') {
                    // do something
                    s3Upload(bucket:"static-jenkins-pipeline-ankitlohchab", includePathPattern:'**/*');
                }
            }
        }
    }
}