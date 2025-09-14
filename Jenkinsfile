pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                echo 'Stage 1: Checking out code from GitHub (8.2CDevSecOps repo)'
            }
        }

        stage('Install Dependencies') {
            steps {
                echo 'Stage 2: Installing dependencies (simulated with echo)'
            }
        }

        stage('Run Tests') {
            steps {
                echo 'Stage 3: Running unit tests (simulated with echo)'
            }
        }

        stage('Generate Coverage Report') {
            steps {
                echo 'Stage 4: Generating coverage report (simulated with echo)'
            }
        }

        stage('NPM Audit (Security Scan)') {
            steps {
                echo 'Stage 5: Running NPM security audit (simulated with echo)'
            }
        }
    }
}
