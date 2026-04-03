pipeline {
    agent any

    stages {
        stage('Build Docker Image') {
            steps {
                sh 'docker build -t myapp .'
            }
        }

        stage('Stop Old Container') {
            steps {
                sh 'docker stop myapp-container || true'
                sh 'docker rm myapp-container || true'
            }
        }

        stage('Run New Container') {
            steps {
                sh 'docker run -d -p 8082:80 --name myapp-container myapp'
            }
        }
    }
}
