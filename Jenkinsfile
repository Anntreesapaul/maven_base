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
            sh 'mvn --settings settings.xml package'
          }
        }
        stage('deploy') {
          steps {
            sh 'mvn --settings settings.xml clean deploy'
          }
        }
      }
    }
  }
}