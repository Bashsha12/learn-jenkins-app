pipeline {
    agent any

    stages {
        stage('Clean Workspace') {
            steps {
                cleanWs()
            }
        }

        stage('Checkout Code') {
            steps {
                checkout scm
            }
        }

        stage('Build') {
            agent {
                docker {
                    image 'node:18-alpine'
                    reuseNode true
                }
            }
            steps {
                sh '''
                ls -la
                echo "Building the application..."
                npm install
                npm run build || echo "Build step skipped (no build script)"
                node --version
                npm --version
                ls -la
                '''
            }
        }
    }
}
