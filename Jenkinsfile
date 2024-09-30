pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                script {
                    sh 'docker run -d --name my-container -p 80:80 nginx'
                }
            }
        }
    }

    post {
        always {
            echo 'Pipeline finished.'
        }
    }
}
