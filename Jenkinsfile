pipeline {
    agent any

    environment {
        DOCKER_BIN = "/usr/local/bin/docker"   // change if yours is different
        PATH = "/usr/local/bin:/opt/homebrew/bin:/usr/bin:/bin:/usr/sbin:/sbin"
    }

    stages {
        stage('build') {
            steps {
                sh '''
                    echo "Docker Location:"
                    which docker
                    docker --version
                    docker run --rm node:18-alpine node -v
                '''
            }
        }
    }
}