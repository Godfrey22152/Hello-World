pipeline {
    agent {
        docker {
            // Use a Node.js with Angular CLI Docker image
            image 'node:14'
            args '-p 4200:4200' // Expose port 4200 for serving the application
        }
    }

    stages {
        stage('Checkout') {
            steps {
                // Checkout the code from your Git repository
                git url: 'https://github.com/Godfrey22152/Hello-World.git'
            }
        }

        stage('Install Dependencies') {
            steps {
                // Install Angular CLI globally
                sh 'npm install -g @angular/cli'
                // Install project dependencies
                sh 'npm install'
            }
        }

        stage('Build') {
            steps {
                // Build the Angular app for production
                sh 'ng build --prod'
            }
        }

        stage('Start Server') {
            steps {
                // Serve the built Angular application using Angular CLI
                sh 'ng serve --prod --host 0.0.0.0 --port 4200'
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
