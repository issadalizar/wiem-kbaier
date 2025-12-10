pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Récupérer le code depuis ton repo
                git branch: 'main', url: 'https://github.com/issadalizar/wiem-kbaier.git'
            }
        }

        stage('Install dependencies') {
            steps {
                // Si tu utilises npm :
                sh 'npm install'
                // ou, si le projet utilise plutôt yarn :
                // sh 'yarn install'
            }
        }

        stage('Tests') {
            steps {
                // Si tu n'as pas de tests, tu peux faire :
                // sh 'npm test || echo "No tests"'
                sh 'npm test'
            }
        }

        stage('Build Docker image') {
            steps {
                sh 'docker build -t todo-app .'
            }
        }
    }
}
