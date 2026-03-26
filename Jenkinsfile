pipeline {
    agent {
        docker {
            image 'node:18-alpine'
        }
    }
    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/vokhoadev/jenkins-demo.git'
            }
        }
        stage('Install') {
            steps {
                sh 'npm install'
            }
        }
        stage('Build') {
            steps {
                sh 'npm run build'
            }
        }
        stage('Test') {
            steps {
                sh 'npm test'
            }
        }

        stage('Deploy') {
            steps {
                sh 'echo "Deploying (demo only)..."'
            }
        }
    }

    post {
        success {
            echo 'Pipeline successed!'
        }
        failure {
            echo 'Pipeline failed!'
        }
    }
}