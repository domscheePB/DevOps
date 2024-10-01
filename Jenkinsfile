pipeline {
    agent any
    stages {
        stage('Test Docker') {
            steps {
                script {
                    sh 'docker --version'
                }
            }
        }
        stage('Run MySQL Container') {
            steps {
                script {
                    sh '''
                    docker run -d \
                    --name my-mysql \
                    -e MYSQL_ROOT_PASSWORD=root_password \
                    -e MYSQL_DATABASE=my_database \
                    -e MYSQL_USER=my_user \
                    -e MYSQL_PASSWORD=my_password \
                    -p 3306:3306 \
                    mysql:latest
                    '''
                }
            }
        }
    }
}
