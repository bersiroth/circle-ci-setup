pipeline {
  agent {
    docker {
      image 'node:8'
    }

  }
  stages {
    stage('lint') {
      steps {
        sh 'npm run lint'
      }
    }
  }
}