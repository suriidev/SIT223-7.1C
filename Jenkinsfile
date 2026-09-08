pipeline {
    agent any

    triggers {
        pollSCM('H/5 * * * *')
    }

    stages {
        stage('Build') {
            steps {
                echo 'Building the application...'
                echo 'Tool used: npm (npm install && npm run build)'
            }
        }

        stage('Unit and Integration Tests') {
            steps {
                echo 'Running unit tests to verify code correctness...'
                echo 'Running integration tests to verify components work together...'
                echo 'Tool used: Jest (npm test)'
            }
        }

        stage('Code Analysis') {
            steps {
                echo 'Analysing code for quality and maintainability issues...'
                echo 'Tool used: ESLint (npx eslint .)'
            }
        }

        stage('Security Scan') {
            steps {
                echo 'Scanning code and dependencies for known vulnerabilities...'
                echo 'Tool used: Snyk (snyk test)'
            }
        }

        stage('Deploy to Staging') {
            steps {
                echo 'Deploying application to staging server...'
                echo 'Tool used: AWS CLI (deploying to an AWS EC2 staging instance)'
            }
        }

        stage('Integration Tests on Staging') {
            steps {
                echo 'Running integration tests against the staging environment...'
                echo 'Tool used: Postman/Newman'
            }
        }

        stage('Deploy to Production') {
            steps {
                echo 'Deploying application to production server...'
                echo 'Tool used: AWS CLI (deploying to an AWS EC2 production instance)'
            }
        }
    }

    post {
        success {
            echo 'Pipeline completed successfully.'
        }
        failure {
            echo 'Pipeline failed. Check logs for details.'
        }
    }
}
