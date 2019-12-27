pipeline {
    agent {
        docker {
            // image 'node:alpine'
            // image 'node:6-alpine'
            // image 'node'
            image 'node:alpine3.11'
            args '-p 3000:3000 -p 5000:5000' 
        }
    }
    environment {
        CI = 'true'
    }
    stages {
        stage('Build') {
            steps {
                // sh 'sudo chown -R 113:117 "/.npm"'
                sh 'npm install'
            }
        }
        stage('Test') {
            steps {
                sh './jenkins/scripts/test.sh'
            }
        }
    }
}
