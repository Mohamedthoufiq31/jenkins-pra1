pipeline {
    agent any

    stages {

        stage('Build') {
            steps {
                echo 'Building application...'
            }
        }

        stage('Test') {
            steps {
                echo 'Testing application...'
            }
        }

        stage('Deploy') {

            when {
                branch 'main'
            }

            steps {
                echo 'Deploying application...'
            }
        }
    }
}