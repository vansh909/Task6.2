pipeline {
    agent any

    stages {
        stage('Install Dependencies') {
            steps {
                echo 'This stage installs all the required dependencies for the React project using npm.'
            }
        }

        stage('Unit Tests') {
            steps {
                echo 'This stage runs unit tests for the React application using Jest to ensure the individual components function as expected.'
            }
            post {
                success {
                    emailext(
                        subject: "Unit Tests Successful",
                        body: "Unit tests passed successfully.",
                        to: "vansh4857.be22@chitkara.edu.in",
                        attachLog: true
                    )
                }
                failure {
                    emailext(
                        subject: "Unit Tests Failed",
                        body: "Unit tests failed. Please check the logs for more details.",
                        to: "vansh4857.be22@chitkara.edu.in",
                        attachLog: true
                    )
                }
            }
        }

        stage('Code Analysis') {
            steps {
                echo 'This stage analyzes the React codebase using ESLint to identify potential issues and ensure it adheres to defined coding standards and best practices.'
            }
        }

        stage('Security Scan') {
            steps {
                echo 'This stage performs a security scan on the React application using OWASP ZAP to identify potential vulnerabilities and security risks.'
            }
            post {
                success {
                    emailext(
                        subject: "Security Scan Successful",
                        body: "Security scan passed successfully.",
                        to: "vansh4857.be22@chitkara.edu.in",
                        attachLog: true
                    )
                }
                failure {
                    emailext(
                        subject: "Security Scan Failed",
                        body: "Security scan failed. Please check the logs for more details.",
                        to: "vansh4857.be22@chitkara.edu.in",
                        attachLog: true
                    )
                }
            }
        }

        stage('Build') {
            steps {
                echo 'This stage builds the React application for production deployment by running the "npm run build" command, which optimizes and bundles the application.'
            }
        }

        stage('Deploy to Staging') {
            steps {
                echo 'This stage deploys the built React application to a staging server, such as an AWS S3 bucket, using the AWS CLI for future testing and verification.'
            }
        }

        stage('Integration Tests on Staging') {
            steps {
                echo 'This stage runs integration tests on the React application deployed to the staging environment using Jest to ensure the application functions as expected in a production-like environment.'
            }
        }

        stage('Deploy to Production') {
            steps {
                echo 'This stage deploys the built React application to a production server, such as an AWS S3 bucket, using the AWS CLI, making it accessible to end-users.'
            }
        }
    }
}
