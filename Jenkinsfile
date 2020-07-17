pipeline {
    agent any
    stages {
        stage('Upload to AWS') {
            steps {
                withAWS(region:'us-west-2') {
                    withAWS(credentials:'aws-static') {
                        withAWS(profile:'jenkins') {
                            s3Upload(file:index.html, bucket:shon-demo, path:/)
                        }
                    }
                }
            }
        }
    }
}
