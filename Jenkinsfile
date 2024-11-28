pipeline {
    agent {
        docker {
            image 'node:18-alpine'
            reuseNode true
        }
    }

    stages {
        stage('Cleanup') {
            steps {
                sh 'rm -rf node_modules'
                sh 'npm cache clean --force'
            }
        }
        stage('Build') {

            steps {
                echo 'Hello World'
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
