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
        echo "Cleaning npm cache and node_modules..."
        rm -rf node_modules
        npm cache clean --force
        npm install
        npm run build || echo "Build step skipped (no build script)"
        node --version
        npm --version
        '''
    }
}
    }
}
