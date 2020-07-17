pipeline {
    agent any
    stages{
        stage('Lint HTML'){
            steps {
                tidy -q -e *.html
            }
        }
        stage('Upload to AWS') {
            steps {
                retry(3){
                withAWS(region:'us-west-2') {
                        withAWS(credentials:'aws-static') {
                            s3Upload(file:'index.html', bucket:'shon-demo', path:'')
                        }
                    }
                }
            }
        }
    }
}
