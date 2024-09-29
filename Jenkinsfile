pipeline {
    agent any

    stages {
      
        stage('Build Docker Images') {
            steps {
                script {
                    // Build Docker images
                    sh 'docker compose -p prod --env-file prod.env up -d --force-recreate --build' 
                }
            }
        }
    }

    post {
        success {
            echo 'Build, tests, and deployment were successful.'
        }
        failure {
            echo 'Build or tests failed.'
        }
    }
}
