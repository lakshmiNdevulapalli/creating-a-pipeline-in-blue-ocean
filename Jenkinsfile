pipeline {
  agent {
    docker {
      args '-p 3000:3000'
      image 'node:8.15.1-alpine'
    }

  }
  stages {
    stage('Build') {
      steps {
        nodejs('nodejs') {
          sh 'npm install'
        }

      }
    }
    stage('Test') {
      environment {
        CI = 'true'
      }
      steps {
        sh './jenkins/scripts/test.sh'
      }
    }
    stage('Deliver') {
      steps {
        sh './jenkins/scripts/deliver.sh'
        echo 'Finished using the website ? (Click "Proceed" to continue)'
        sh './jenkins/scripts/kill.sh'
      }
    }
  }
  environment {
    HOME = '.'
  }
}