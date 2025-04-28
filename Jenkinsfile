pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
                sh '''
                echo Hello World
                ls -la
                touch Test.txt
                ls -la
                pwd
                '''
            }
        }
        
    }
}
