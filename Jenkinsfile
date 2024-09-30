pipeline {
    agent any
    environment {
        MYSQL_ROOT_PASSWORD = 'root'
        MYSQL_DATABASE = 'mydatabase'
        MYSQL_USER = 'user'
        MYSQL_PASSWORD = 'password'
    }
    stages {
        stage('Build') {
            steps {
                echo 'Construyendo...'
            }
        }
        stage('Deploy MySQL') {
            steps {
                script {
                    docker.image('mysql:latest').run('-d -e MYSQL_ROOT_PASSWORD=${MYSQL_ROOT_PASSWORD} -e MYSQL_DATABASE=${MYSQL_DATABASE} -e MYSQL_USER=${MYSQL_USER} -e MYSQL_PASSWORD=${MYSQL_PASSWORD} -p 3306:3306 --name my-mysql')
                }
            }
        }
    }
    post {
        always {
            echo 'Pipeline finalizado'
        }
    }
}
