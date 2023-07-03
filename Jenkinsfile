pipeline {
  agent any
  stages {
    stage('SCM') {
      steps {
        checkout scm
      }
    }

    stage('Compile') {
      agent {
        docker {
          image 'maven:3.6.0-jdk-8-alpine'
          reuseNode true
          args '-v/root/.m2/repository:/root/.m2/repository'
        }

      }
      steps {
        sh ' mvn clean compile'
      }
    }

  }
}