pipeline {
    agent any

    stages {
        stage('Stage 1: Checkout') {
            steps {
                echo 'Stage 1: Checking out code from GitHub (simulated for demo)'
            }
        }

        stage('Stage 2: Install Dependencies') {
            steps {
                echo 'Stage 2: Installing dependencies (npm install simulated)'
            }
        }

        stage('Stage 3: Run Tests') {
            steps {
                echo 'Stage 3: Running tests (simulated)'
            }
            post {
                always {
                    emailext(
                        to: 'sathvik.chinthalapani@gmail.com',
                        subject: "Stage 3 - Run Tests Completed",
                        body: "Run Tests stage finished. See Jenkins console for details.",
                        attachLog: true
                    )
                }
            }
        }

        stage('Stage 4: Generate Coverage Report') {
            steps {
                echo 'Stage 4: Generating coverage report (simulated)'
            }
        }

        stage('Stage 5: NPM Audit (Security Scan)') {
            steps {
                echo 'Stage 5: Running NPM Audit (simulated)'
            }
            post {
                always {
                    emailext(
                        to: 'sathvik.chinthalapani@gmail.com',
                        subject: "Stage 5 - Security Scan Completed",
                        body: "NPM Audit stage finished. See Jenkins console for vulnerabilities.",
                        attachLog: true
                    )
                }
            }
        }
    }
}
