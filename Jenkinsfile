pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo "Building the code via Maven"
            }
        }
        stage('Unit and Integration Tests') {
            steps {
                echo "Executing unit tests with JUnit"
                echo "Executing integration tests with Selenium"
            }
        }
        stage('Code Analysis') {
            steps {
                echo "Analyzing the code via SonarQube"
            }
        }
        stage('Security Scan') {
            steps {
                echo "Conducting a security scan using OWASP ZAP"
            }
        }
        stage('Deploy to Staging') {
            steps {
                echo "Deploying the application to stage server"
            }
        }
        stage('Integration Tests on Staging') {
            steps {
                echo "Executing integration tests on the staging environment"
            }
        }
        stage('Deploy to Production') {
            steps {
                echo "Deploying the application to production server"
            }
        }
    }
        post{
            success{
             emailext attachLog: true, body: 'Pipeline was successful, please see attached logs.', subject: 'PIPELINE STATUS NOTIFICATION',  to: 'kookaiisidro01@gmail.com'
        }
    }
}
