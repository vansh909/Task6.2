pipeline {
    agent any

    stages {
        stage('Install Dependencies') {
            steps {
                echo 'Install all necessary dependencies for the React project using npm.'
            }
        }

        stage('Unit Tests') {
            steps {
                echo 'Execute unit tests for the React application using Jest to ensure individual components operate as expected.'
            }
            post {
                success {
                    emailext(
                        subject: "Unit Tests Successful",
                        body: "Unit tests have been successfully passed.",
                        to: "vansh4857.be22@chitkara.edu.in, shravan4841.be22@chitkara.edu.in", // Corrected syntax
                        attachLog: true
                    )
                }
                failure {
                    emailext(
                        subject: "Unit Tests Failed",
                        body: "Unit tests have failed. Please examine the logs for further information.",
                        to: "vansh4857.be22@chitkara.edu.in, shravan4841.be22@chitkara.edu.in", // Corrected syntax
                        attachLog: true
                    )
                }
            }
        }

        stage('Code Analysis') {
            steps {
                echo 'Inspect the React codebase using ESLint to pinpoint potential issues and ensure compliance with coding standards and best practices.'
            }
        }

        stage('Security Scan') {
            steps {
                echo 'Conduct a security scan on the React application using OWASP ZAP to uncover possible vulnerabilities and security threats.'
            }
            post {
                success {
                    emailext(
                        subject: "Security Scan Successful",
                        body: "The security scan has been successfully completed.",
                        to: "vansh4857.be22@chitkara.edu.in, shravan4841.be22@chitkara.edu.in", // Corrected syntax
                        attachLog: true
                    )
                }
                failure {
                    emailext(
                        subject: "Security Scan Failed",
                        body: "The security scan has failed. Please check the logs for more details.",
                        to: "vansh4857.be22@chitkara.edu.in, shravan4841.be22@chitkara.edu.in", // Corrected syntax
                        attachLog: true
                    )
                }
            }
        }

        stage('Build') {
            steps {
                echo 'Assemble the React application for production deployment by executing the "npm run build" command, which optimizes and bundles the application.'
            }
        }

        stage('Deploy to Staging') {
            steps {
                echo 'Send the assembled React application to a staging server, such as an AWS S3 bucket, using the AWS CLI for subsequent testing and validation.'
            }
        }

        stage('Integration Tests on Staging') {
            steps {
                echo 'Conduct integration tests on the React application deployed to the staging environment using Jest to ensure proper functionality in a production-like setting.'
            }
        }

        stage('Deploy to Production') {
            steps {
                echo 'Dispatch the assembled React application to a production server, such as an AWS S3 bucket, using the AWS CLI, thus making it available to end-users.'
            }
        }
    }
}
