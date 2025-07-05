pipeline {
    agent any

    stages {
        stage('w/o docker') {
            steps {
                sh 'echo "Without docker"'
                sh 'touch catfile.txt'
                //sh 'echo "catfile">> w/o docker/catfile.txt
            }
        }

        stage('w/ docker') {
            agent {
                docker {
                    image 'node:18-alpine'
                }
            }
            steps {
                sh 'echo "With docker"'
                sh 'npm --version'
            }
        }
    }
}