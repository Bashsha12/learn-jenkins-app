pipeline {
    agent any

    stages {
        stage('Clean Workspace') {
            steps {
                cleanWs()
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
                npm ci
                npm run build
                node --version
                npm --version
                ls -la
                '''
            }
        }
    }
}
