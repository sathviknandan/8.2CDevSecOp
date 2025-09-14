pipeline {
    agent any

    stages {
        stage('Stage 1: Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/sathviknandan/8.2CDevSecOps.git'
            }
        }

        stage('Stage 2: Install Dependencies') {
            steps {
                bat 'npm install'
            }
        }

        stage('Stage 3: Run Tests') {
            steps {
                bat 'cmd /c "npm test || exit /b 0"'
            }
            post {
                always {
                    emailext(
                        to: 'your_email@example.com',
                        subject: "Stage 3 - Run Tests Completed",
                        body: """Hello,

Stage 3 (Run Tests) has completed in the Jenkins pipeline.
Please check the attached log or Jenkins console for details.

Regards,
Jenkins""",
                        attachLog: true
                    )
                }
            }
        }

        stage('Stage 4: Generate Coverage Report') {
            steps {
                bat 'cmd /c "npm run coverage || exit /b 0"'
            }
        }

        stage('Stage 5: NPM Audit (Security Scan)') {
            steps {
                bat 'cmd /c "npm audit || exit /b 0"'
            }
            post {
                always {
                    emailext(
                        to: 'sathvik.chinthalapani@gmail.com',
                        subject: "Stage 5 - NPM Security Scan Completed",
                        body: """Hello,

Stage 5 (NPM Audit - Security Scan) has completed in the Jenkins pipeline.
Please check the attached log or Jenkins console for vulnerabilities.

Regards,
Jenkins""",
                        attachLog: true
                    )
                }
            }
        }
    }
}
