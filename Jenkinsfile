pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
              
                git branch: 'main', url: 'https://github.com/issadalizar/wiem-kbaier.git'
            }
        }

        stage('Install dependencies') {
            steps {
                // Commande Windows
                bat 'npm install'
            }
        }

        stage('Tests') {
            steps {
                // Si tu n'as pas de tests, mets plutôt :
                // bat 'npm test || echo No tests'
                bat 'npm test'
            }
        }

        stage('Build Docker image') {
            steps {
                // Docker doit être installé sur la machine Jenkins
                bat 'docker build -t todo-app .'
            }
        }
    }
}
