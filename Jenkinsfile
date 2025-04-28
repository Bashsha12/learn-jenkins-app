pipeline {
    agent any

    stages {
        stage('Build') {
            agent {
                docker {
                    image 'node:23-alpine'
                    reuseNode true
                }
            }
            steps {
                script {
                    // Ensuring the npm cache folder permissions are set correctly without sudo
                    sh 'echo "Cleaning npm cache and node_modules..."'
                    sh 'rm -rf node_modules'
                    sh 'npm cache clean --force'
                    sh 'npm install || echo "npm install failed, continuing..."'
                    sh 'npm run build "'
                    sh 'node --version'
                    sh 'echo "Hello Welcome to Jenkins"'
                    sh 'npm --version'
                    sh 'ls -la'
                }
            }
        }
    }
}
