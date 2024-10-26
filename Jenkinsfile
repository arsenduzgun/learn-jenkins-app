pipeline {
    agent any

    stages {
        agent {
            docker {
                reuseNode True
                image 'node:18-alpine'
            }
        }
        stage('build') {
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
