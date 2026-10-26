pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                echo 'Abbas Store: Checking out GitHub code'
                checkout scm
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t abbas-store:v1 .'
            }
        }

        stage('Deploy Abbas Store') {
            steps {
                sh '''
                    docker stop abbas-store
                    docker rm abbas-store
                    docker run -d --name abbas-store -p 8081:80 --restart unless-stopped abbas-store:v1
                '''
            }
        }
    }
}
