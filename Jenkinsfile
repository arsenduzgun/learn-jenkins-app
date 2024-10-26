pipeline {
    agent any

    stages {
        
        stage('build') {
            agent {
                docker {
                    reuseNode true
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
        stage('test') {
            agent {
                docker {
                    reuseNode true
                    image 'node:18-alpine'
                }
            }
            steps {
                sh '''
                    test -f build/index.html
                    npm test
                '''
            }
        }
    }
}
