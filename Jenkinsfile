pipeline {
  agent {
    docker {
      image 'node:8'
    }

  }
  stages {
    stage('error') {
      steps {
        sh 'npm run lint'
      }
    }
  }
}