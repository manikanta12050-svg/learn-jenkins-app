pipeline {
    agent {
        docker {
            image 'node:18'
        }
    }

    stages {
        stage('Check Node') {
            steps {
                sh 'node -v'
            }
        }
    }
}