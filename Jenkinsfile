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

        stage('Run Tests') {
            steps {
                // Ganti <app_container_name> sesuai dengan nama container di docker-compose
                sh 'docker exec <app_container_name> run-your-tests.sh'
            }
        }

        stage('Stop Containers') {
            steps {
                sh 'docker compose -f ./tests/docker-compose-postgres.yml down'
            }
        }
    }
}