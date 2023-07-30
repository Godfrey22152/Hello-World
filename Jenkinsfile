pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Checkout the code from your Git repository
                git url: 'https://github.com/Godfrey22152/Hello-World.git'
            }
        }

        stage('Build and Run') {
            steps {
                // Add any build or run steps for your Hello-World Angular application here
                // For example, you can install dependencies and serve the application
                sh 'npm install'
                sh 'npm start'
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
