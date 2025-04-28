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
            steps{
                cleanWs()
            }
            steps {
                sh '''
                ls -la
                echo "Building the application..."
                # Install dependencies and build the application
                # The npm ci command is used to install dependencies from package-lock.json
                npm ci
                # The npm run build command is used to build the application

                npm run build
                 node --version
                 npm --version
                ls -la
                '''
            }
        }
        
    }
}
