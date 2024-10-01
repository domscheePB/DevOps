pipeline {
    agent any
    stages {
        stage('Test Docker') {
            steps {
                script {
                    sh 'docker --version'
                    sh 'docker ps'
                }
            }
        }
        stage('Run MySQL Container') {
            steps {
                script {
                    sh '''
                        docker run -d --name my_mysql -e MYSQL_ROOT_PASSWORD=root -e MYSQL_DATABASE=mydb -p 3306:3306 mysql:latest
                    '''
                }
            }
        }
    }
}
