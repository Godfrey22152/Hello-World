pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
                echo 'HELLO WORLD'
            }
        }
    }

    post {
        always {
            // Clean up any temporary files or artifacts after the build and deployment
            deleteDir()
        }

        success {
            echo 'Build and deployment successful!'
        }

        failure {
            echo 'Build or deployment failed. Please check the logs for more details.'
        }
    }
}
