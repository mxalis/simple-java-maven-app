pipeline {
  agent any
  stages {
    stage('Initialize') {
      steps {
        echo 'Test Message'
      }
    }
    stage('Compile') {
      steps {
        bat 'mvn clean compile'
      }
    }
    stage('Unit Test') {
      steps {
        bat 'mvn test'
      }
    }
    stage('Package') {
      steps {
        bat 'mvn package'
      }
    }
  }
}