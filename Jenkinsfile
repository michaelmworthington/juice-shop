pipeline {
  agent {
    docker {
      image 'node:9-alpine'
    }

  }
  stages {
    stage('Build') {
      steps {
        sh 'npm install'
      }
    }
    stage('Policy Evaluation Dev') {
      steps {
        nexusPolicyEvaluation(iqApplication: 'JuiceShop', iqScanPatterns: [[scanPattern: '**/*']], iqStage: 'build')
      }
    }
  }
  environment {
    HOME = '.'
  }
}