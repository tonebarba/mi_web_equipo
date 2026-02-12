pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                echo 'El código ya está en el workspace de Jenkins'
            }
        }

        stage('Desplegar web (copiar archivos)') {
            steps {
                sh '''
                rm -rf /var/jenkins_home/web/*
                cp -r ./* /var/jenkins_home/web/
                '''
            }
        }
    }

    post {
        success {
            echo 'Despliegue completado correctamente'
        }
        failure {
            echo 'Error en el despliegue'
        }
    }
}