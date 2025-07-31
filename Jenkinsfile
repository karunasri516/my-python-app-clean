pipeline {
    agent any

    stages {
        stage('Checkout Code') {
            steps {
                git 'https://github.com/karunasri516/my-pthon-app.git'
            }
        }

        stage('Install Python & Dependencies') {
            steps {
                sh 'python3 --version'
                sh 'pip3 install -r requirements.txt || true'
            }
        }

        stage('Run Tests') {
            steps {
                sh 'python3 test_app.py'
            }
        }

        stage('Build Artifact') {
            steps {
                sh 'zip -r app-package.zip .'
            }
        }
    }

    post {
        success {
            echo '✅ Build completed successfully!'
        }
        failure {
            echo '❌ Build failed.'
        }
    }
}

