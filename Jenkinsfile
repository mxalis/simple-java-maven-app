pipeline {
  agent any
  stages {
    stage('Initialize') {
      steps {
        echo 'PATH = ${PATH}'
        echo 'JAVA_HOME = ${JAVA_HOME}'
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
        archiveArtifacts '**/target/*.jar'
      }
    }
    stage('Quality Check') {
      steps {
        waitForQualityGate true
      }
    }
  }
  environment {
    JAVA_PATH = 'C:\\Program Files\\Java\\jdk1.8.0_92'
    JAVA_HOME = 'C:\\Program Files\\Java\\jdk1.8.0_92'
  }
}