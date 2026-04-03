pipeline {
    agent any

    stages {
        stage('Deploy Website') {
            steps {
                sh '''
                cd $WORKSPACE
                pkill -f "python3 -m http.server" || true
                nohup python3 -m http.server 8081 > server.log 2>&1 &
                '''
            }
        }
    }
}
