pipeline {
    agent any

    stages {
        stage('Deploy archivos al SFTP') {
            steps {
                sh '''
                echo "Archivos desplegados en el servidor SFTP"
                ls -l *.txt
                '''
            }
        }
    }

    post {
        success {
            echo 'Despliegue SFTP completado'
        }
        failure {
            echo 'Error en el despliegue'
        }
    }
}