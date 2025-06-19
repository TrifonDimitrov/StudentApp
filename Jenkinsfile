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
        stage('Security Audit') {
            steps {
                bat 'npm audit'
            }
        }
        stage('Deploy to Render') {
            steps {
                input message: 'Approve deployment?', ok: 'Deploy'
                bat 'echo Deploying application...'
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