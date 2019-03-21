pipeline {
  agent {
    docker {
      args '-p 3000:3000'
      image 'node:7-alpine'
    }

  }
  stages {
    stage('Build') {
      steps {
        sh 'npm install'
        nodejs('nodejs') {
          sh 'npm install'
        }

      }
    }
  }
  environment {
    HOME = '.'
  }
}