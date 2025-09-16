pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'master', url: 'https://github.com/Vamsikrishnareddy-vkr/nodejs-ci-app.git'
            }
        }

        stage('Install Dependencies') {
            steps {
                bat 'npm install'
            }
        }

        stage('Run Tests') {
            steps {
                echo "Running tests..."
                bat 'npm test'
            }
        }

        stage('Build Docker Image') {
            steps {
                script {
                    docker.build("nodejs-ci-app")
                }
            }
        }
    }
}


