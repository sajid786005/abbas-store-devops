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
    }
}
