pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
                echo 'HELLO WORLD'
            }
        }  
    }

        success {
            echo 'Build and deployment successful!'
        }

        failure {
            echo 'Build or deployment failed. Please check the logs for more details.'
        }
    }
}
