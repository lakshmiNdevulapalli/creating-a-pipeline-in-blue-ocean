pipeline {
  agent {
    docker {
      image 'node:6-alpine'
      args '-p 3000:3000'
      args '-v /var/run/docker.sock:/var/run/docker/sock'
      args '--group-add 978'
    }

  }
  stages {
    stage('Build') {
      steps {
        sh 'npm install'
      }
    }
  }
}
