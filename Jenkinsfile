pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/<your_github_username>/8.2CDevSecOps.git'
            }
        }

        stage('Install Dependencies') {
            steps {
                // Install project dependencies
                bat 'npm install'
            }
        }

        stage('Run Tests') {
            steps {
                // Run unit tests; continue even if they fail
                bat 'npm test || exit /b 0'
            }
        }

        stage('Generate Coverage Report') {
            steps {
                // Generate coverage report if available
                bat 'npm run coverage || exit /b 0'
            }
        }

        stage('NPM Audit (Security Scan)') {
            steps {
                // Scan for known vulnerabilities in dependencies
                bat 'npm audit || exit /b 0'
            }
        }
    }
}
