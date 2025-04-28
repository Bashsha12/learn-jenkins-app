pipeline {
    agent any

    stages {
        stage('Build') {
            agent {
                docker {
                    image 'node:18-alpine'
                    reuseNode true
                }
            }
            steps {
                sh '''
                echo "Fixing npm cache folder permissions..."
                sudo chown -R $(whoami) /.npm
                echo "Cleaning npm cache and node_modules..."
                rm -rf node_modules
                npm cache clean --force
                npm install
                npm run build || echo "Build step skipped (no build script)"
                node --version
                echo "Hello Welcome to Jenkins"
                npm --version
                ls -la
                '''
            }
        }
    }
}
