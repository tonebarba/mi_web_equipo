pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                echo 'Código descargado automáticamente'
            }
        }

        stage('Build Docker image') {
            steps {
                sh 'docker build -t mi_web:latest .'
            }
        }

        stage('Deploy con docker-compose') {
            steps {
                sh 'docker compose up -d --build'
            }
        }
    }

    post {
        success {
            echo 'Despliegue completado'
        }
        failure {
            echo 'Fallo en el pipeline'
        }
    }
}