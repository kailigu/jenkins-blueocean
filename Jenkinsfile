pipeline {
    agent any
    stages {
        stage('Lint HTML') {
            steps {
                sh 'echo "Verify all html files."'
                sh 'tidy -q -e *.html'
            }
        }    
        stage("Upload to AWS") {
            steps {
                withAWS(region:'ap-southeast-2', credentials:'aws-static') {
                    sh 'echo "Uploading content to S3 with AWS credentials"'
                    s3Upload(pathStyleAccessEnabled: true, payloadSigningEnabled: true, file:'index.html', bucket:'udacity-jenkins-kailigu')
                }
            }
        }
    }
}