pipeline {
  agent any
  stages {
    stage('init') {
      steps {
        script {
         def sbtHome = tool 'sbt 1.0.0-M4'
         env.sbt= "${sbtHome}/bin/sbt -no-colors -batch"
        }
      }
    }
    stage('Build') {
        steps {
          sh "${sbt} 'set test in assembly := {}' assembly"
          archive includes: 'target/scala-*/toto.jar'
        }
    }
    stage('Test') {
        when { branch 'master' }
        agent { docker 'openjdk:7-jre' }
        steps {
          echo 'Hello, JDK'
          sh 'java -version'
        }
    }
  }
}
