pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh 'ping -c 1 localhost.'
      }
    }
    stage('Test') {
      steps {
        sh 'ping -c 2 localhost'
      }
    }
    stage('Depoly') {
      steps {
        sh 'ping -c 3 localhost'
      }
    }
  }
}