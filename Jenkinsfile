pipeline {
    agent any

    stages {
        
        stage('build') {
            agent {
                docker {
                    reuseNode True
                    image 'node:18-alpine'
                }
            }
            steps {
                sh '''
                    ls -la
                    node --version
                    npm --version
                    npm ci
                    npm run build
                    ls -la
                '''
            }
        }
    }
}
