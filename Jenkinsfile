pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        bat 'gradle build'
      }
    }
    stage('Browser Test') {
      parallel {
        stage('Test') {
          steps {
            
            bat 'gradle test'
              publishHTML([allowMissing: true, alwaysLinkToLastBuild: false, keepAll: true, reportDir: 'julid/build/reports/tests', reportFiles: 'index.html', reportName: 'JUnit Test Reports'])
        publishHTML([allowMissing: true, alwaysLinkToLastBuild: false, keepAll: true, reportDir: 'julid/build/reports/jacoco', reportFiles: 'index.html', reportName: 'JaCoCo Coverage Reports'])
          }
        }
        stage('Chrome') {
          steps {
            echo 'Chrome browser test'
          }
        }
        stage('Safari') {
          steps {
            echo 'Safari Test'
          }
        }
        stage('IE Test') {
          steps {
            echo 'Internet Explorer'
          }
        }
      }
    }
    stage('Sonarqube') {
      steps {
        bat 'gradle clean sonarqube'
      }
    }
    stage('code coverage') {
      steps {
        sh 'gradle jacocoTestReport'
      }
    }
  }
}
