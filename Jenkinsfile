pipeline {

    agent any

    stages {

        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build') {
            steps {
                echo 'Build started automatically!'
                sh 'echo "Commit received from GitHub"'
            }
        }

        stage('Verify') {
            steps {
                sh '''
                    echo "Current directory:"
                    pwd

                    echo "Files:"
                    ls -la

                    echo "Laaatest commit:"
                    git log -1 --oneline
                '''
            }
        }
    }

    post {
        success {
            echo 'Webhook build completed successfully!'
        }

        failure {
            echo 'Webhook build failed!'
        }
    }
}