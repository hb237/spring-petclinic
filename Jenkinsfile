pipeline {
  agent {
    docker {
      image 'openjdk:8-alpine'
      args '-p 3000:3000'
    }

  }
  stages {
    stage('Build') {
      steps {
        sh 'sh "pwd"'
      }
    }

  }
}