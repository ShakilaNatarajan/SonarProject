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
  }
}