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
          image 'huangzp88/maven-openjdk17'
        }

      }
      steps {
        sh 'mvn clean compile'
      }
    }

  }
}