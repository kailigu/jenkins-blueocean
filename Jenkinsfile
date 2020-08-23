pipeline {
    agent any
    stages {
        stage("Upload to AWS") {
            steps {
                sh '''
                    echo "Multiline shell steps works too"
                    pwd
                    ls -lah
                '''
            }
        }
    }
}