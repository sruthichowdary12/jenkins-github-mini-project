
pipeline {
    agent any

    options {
        timestamps()
    }

    stages {
        stage('Checkout') {
            steps {
                echo 'Source code is available in the workspace.'
                sh 'pwd'
                sh 'ls -la'
            }
        }

        stage('Validate Project') {
            steps {
                sh '''
                    set -eu
                    test -f README.md
                    test -f Jenkinsfile
                    echo "Required files are present."
                '''
            }
        }

        stage('Build') {
            steps {
                sh '''
                    echo "Running sample build..."
                    echo "Repository validation completed - version 2."
                    echo "Build number: $BUILD_NUMBER"
                '''
            }
        }
    }

    post {
        success {
            echo 'Pipeline completed successfully.'
        }
        failure {
            echo 'Pipeline failed. Check the console log.'
        }
    }
}
