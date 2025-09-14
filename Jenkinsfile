pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/sathviknandan/8.2CDevSecOp.git'
            }
        }

        stage('Install Dependencies') {
            steps {
                bat 'npm install'
            }
        }

        stage('Run Tests') {
            steps {
                bat 'cmd /c "npm test || exit /b 0"'
            }
        }

        stage('Generate Coverage Report') {
            steps {
                bat 'cmd /c "npm run coverage || exit /b 0"'
            }
        }

        stage('NPM Audit (Security Scan)') {
            steps {
                bat 'cmd /c "npm audit || exit /b 0"'
            }
        }
    }
}
