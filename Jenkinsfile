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
                    ls -la
                    echo "Node Version:"
                    node -v
                    echo "Npm Version:"
                    npm -v
                    npm ci
                    npm run build
                    ls -la
                '''
            }
        }
    }
}