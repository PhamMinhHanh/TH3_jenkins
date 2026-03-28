pipeline {
    agent {
        docker {
            image 'node:18-alpine'
        }
    }
    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/PhamMinhHanh/TH3_jenkins.git'
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