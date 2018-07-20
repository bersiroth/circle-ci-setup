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
    stage('test') {
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
          agent {
            docker {
              image 'cypress/base:8'
            }

          }
          steps {
            sh 'npm install'
            sh 'npm run test:e2e:headless	'
            archiveArtifacts 'tests/e2e/videos'
          }
        }
      }
    }
  }
}