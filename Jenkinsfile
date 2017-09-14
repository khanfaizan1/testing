pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh 'ping -c 1 35.185.250.150'
      }
    }
    stage('Test') {
      steps {
        parallel(
          "Test": {
            sh 'ping -c 2 35.185.250.150'
            
          },
          "More Test": {
            sh 'ping -c 35.185.250.150'
            
          }
        )
      }
    }
    stage('Depoly') {
      steps {
        sh 'ping -c 3 35.185.250.150'
      }
    }
  }
}