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
                    node --version
                    npm --version
                    sudo npm install -g npm@10.9.1
                    npm run build
                    ls -la
                '''
            }
        }
    }
}
