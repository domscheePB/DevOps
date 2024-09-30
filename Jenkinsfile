pipeline {
    agent any

    stages {
        stage('Clonar Repositorio') {
            steps {
                git 'https://github.com/domscheePB/DevOps'
            }
        }

        stage('Levantar Base de Datos') {
            steps {
                script {
                    def db = docker.image('mysql:latest')
                    db.run('-e MYSQL_ROOT_PASSWORD=root -e MYSQL_DATABASE=mi_bd')
                }
            }
        }

        stage('Ejecutar Pruebas') {
            steps {
                echo 'Ejecutando pruebas...'
            }
        }
    }

    post {
        always {
            echo 'Pipeline terminado.'
        }
    }
}
