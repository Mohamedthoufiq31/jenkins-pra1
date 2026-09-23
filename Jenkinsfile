pipeline {

    agent any

    environment {
        APP_NAME = 'myapp'
        ENVIRONMENT = 'development'
        TOMCAT_PORT = '9090'
    }

    stages {

        stage('Build') {
            steps {
                echo "===== BUILD ====="
                echo "Application: ${APP_NAME}"
                echo "Environment: ${ENVIRONMENT}"
            }
        }

        stage('Test') {
            steps {
                echo "===== TEST ====="
                echo "Testing ${APP_NAME}"
            }
        }

        stage('Deploy') {
            steps {
                echo "===== DEPLOY ====="
                echo "Deploying ${APP_NAME}"
                echo "Environment: ${ENVIRONMENT}"
                echo "Tomcat Port: ${TOMCAT_PORT}"
            }
        }
    }
}