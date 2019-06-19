pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        bat 'gradle build'
      }
    }
    stage('Test') {
      steps {
        bat 'gradle test'
      }
    }
    stage('Sonarqube') {
      steps {
        bat 'gradle clean sonarqube'
      }
    }
  }
}