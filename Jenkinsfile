pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Start Containers') {
            steps {
                sh 'docker compose -f ./tests/docker-compose-postgres.yml up -d'
            }
        }

        stage('Stop Containers') {
            steps {
                sh 'docker compose -f ./tests/docker-compose-postgres.yml down'
            }
        }
    }
}