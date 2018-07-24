pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        sh 'mvn clean install'
      }
    }
    stage('test') {
      parallel {
        stage('test') {
          steps {
            sh 'mvn -Dtest=TestApp test'
          }
        }
        stage('deploy') {
          steps {
            sh 'mvn clean deploy'
          }
        }
      }
    }
  }
}