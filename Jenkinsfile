pipeline {
    agent any

    environment {
        SFTP_USER = "equipo"
        SFTP_PASS = "password"
        SFTP_HOST = "localhost"
        SFTP_PORT = "2222"
        SFTP_PATH = "/home/equipo/shared"
    }

    stages {
        stage('Enviar archivos al SFTP') {
            steps {
                // Instala sshpass si hace falta
                sh '''
                echo "Enviando archivos al servidor SFTP..."
                sshpass -p $SFTP_PASS scp -P $SFTP_PORT personaA.txt personaB.txt $SFTP_USER@$SFTP_HOST:$SFTP_PATH/
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