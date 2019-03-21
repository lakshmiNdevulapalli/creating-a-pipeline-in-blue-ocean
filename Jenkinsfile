pipeline {
  agent {
    docker {
      args '-p 3000:3000'
      image 'node:8.1-alpine'
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