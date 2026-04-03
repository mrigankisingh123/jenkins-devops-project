pipeline {
    agent any

    stages {
        stage('Build Docker Image') {
            steps {
                sh 'sudo docker build -t myapp .'
            }
        }

        stage('Stop Old Container') {
            steps {
                sh 'sudo docker stop myapp-container || true'
                sh 'sudo docker rm myapp-container || true'
            }
        }

        stage('Run New Container') {
            steps {
                sh 'sudo docker run -d -p 8082:80 --name myapp-container myapp'
            }
        }
    }
}
