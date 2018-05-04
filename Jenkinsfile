pipeline {
    agent {
        docker {
            image 'node:9-alpine' 
        }
    }
	stages {
		stage('Build'){
			steps {
                //nodejs('nodjs_9_11_1_auto') {
                    sh 'npm install'
                //}
			}		
      	}
		stage('Policy Evaluation Dev'){
			steps {
        			nexusPolicyEvaluation failBuildOnNetworkError: false, iqApplication: 'JuiceShop', iqScanPatterns: [[scanPattern: '**/*']], iqStage: 'build', jobCredentialsId: ''
				//nexusPolicyEvaluation iqApplication: 'JuiceShop', iqStage: 'build'
			}
		}
	}
}
