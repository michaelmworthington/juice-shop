pipeline {
	agent any
	stages {
		stage('Build'){
			steps {
          nodejs('nodjs_9_11_1_auto') {
            npm install
          }
      }
    } 
		stage('Policy Evaluation Dev'){
			steps {
        nexusPolicyEvaluation failBuildOnNetworkError: false, iqApplication: 'JuiceShop', iqScanPatterns: [[scanPattern: '**/*']], iqStage: 'build', jobCredentialsId: ''
			}
		}
	}
}
