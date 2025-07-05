pipeline {
    agent any

    stages {
        stage('Test') {
            steps {
                sh 'echo "Without docker"'
                sh 'touch catfile.txt'
                //sh 'echo "catfile">> w/o docker/catfile.txt
            }
        }

        stage('Build') {
            agent {
                docker {
                    image 'node:18-alpine'
                    reuseNode true
                }
            }
            steps {
                sh 'echo "With docker"'
                sh 'npm --version'
                sh '''
                ls -la
                node --version
                npm --version
                npm ci
                npm run build
                ls-la
                '''
            }
        }
    }
}