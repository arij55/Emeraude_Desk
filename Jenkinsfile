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
          reuseNode true
          args '-v/root/.m2/repository:/root/.m2/repository'
          image 'simaofsilva/maven-openjdk11-alpine'
        }

      }
      steps {
        sh '''mvn install  
mvn clean compile'''
      }
    }

  }
}