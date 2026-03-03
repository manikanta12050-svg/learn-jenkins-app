pipeline {
    agent any

    environment {
        PATH = "/opt/homebrew/bin:/usr/local/bin:/usr/bin:/bin:/usr/sbin:/sbin"
    }

    stages {

        stage('Check Docker on Host') {
            steps {
                sh '''
                    echo "Checking Docker on Jenkins host..."
                    which docker
                    docker --version
                    docker ps
                '''
            }
        }

        stage('Build Inside Docker') {
            agent {
                docker {
                    image 'node:18-alpine'
                    reuseNode true
                    args '-v /var/run/docker.sock:/var/run/docker.sock'
                }
            }

            steps {
                sh '''
                    echo "Inside Docker container"
                    ls -la
                    node --version
                    npm --version
                '''
            }
        }
    }
}