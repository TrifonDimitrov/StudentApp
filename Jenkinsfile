pipeline {
    agent any

    stages {
        stage('Checkout the repository') {
            steps {
                checkout scm
            }
        }
        stage('Install Dependencies') {
            steps {
                bat 'npm install'
            }
        }
        stage('Test') {
            steps {
                bat 'npm test'
            }
        }
    }

    post {
        always {
            echo 'Pipelene completed'
        }
        success {
            echo 'Build succeeded'
        }
        failure {
            echo 'Build failed'
        } 
    }
}