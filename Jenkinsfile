pipeline {
  agent {
    docker {
      image 'node:8'
    }

  }
  stages {
    stage('install') {
      steps {
        sh 'npm install'
      }
    }
    stage('lint') {
      parallel {
        stage('lint') {
          steps {
            sh 'npm run lint'
          }
        }
        stage('test:unit') {
          steps {
            sh 'npm run test:unit'
          }
        }
        stage('test:e2e') {
          steps {
            sh 'npm run test:e2e:headless'
          }
        }
      }
    }
  }
}