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
      post {
        always {
          emailext attachLog: true, 
                   body: "Unit and Integration Tests - ${currentBuild.result}", 
                   subject: "Unit and Integration Tests - PIPELINE STATUS NOTIFICATION",
                   to: 'kookaiisidro01@gmail.com'
        }
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
      post {
        always {
          emailext attachLog: true, 
                   body: "Security Scan - ${currentBuild.result}", 
                   subject: "Security Scan - PIPELINE STATUS NOTIFICATION",
                   to: 'kookaiisidro01@gmail.com'
        }
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
}
