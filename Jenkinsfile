pipeline {

    agent any

    parameters {

        choice(
            name: 'ENVIRONMENT',
            choices: [
                'development',
                'testing',
                'production'
            ],
            description: 'Select deployment environment'
        )

        booleanParam(
            name: 'RUN_TESTS',
            defaultValue: true,
            description: 'Run tests?'
        )
    }

    stages {

        stage('Build') {
            steps {
                echo "===== BUILD ====="
                echo "Building application"
            }
        }

        stage('Test') {

            when {
                expression {
                    params.RUN_TESTS
                }
            }

            steps {
                echo "===== TEST ====="
                echo "Running tests"
            }
        }

        stage('Production Approval') {

            when {
                expression {
                    params.ENVIRONMENT == 'production'
                }
            }

            steps {
                input message: 'Production deployment approved?'
            }
        }

        stage('Deploy') {
            steps {
                echo "===== DEPLOY ====="
                echo "Deploying to ${params.ENVIRONMENT}"
            }
        }
    }

    post {

        success {
            echo 'Pipeline completed successfully'
        }

        failure {
            echo 'Pipeline failed'
        }

        always {
            echo 'Pipeline finished'
        }
    }
}