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
                rsync -av --delete \
                --exclude='.git' \
                ./ /var/jenkins_home/web/
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