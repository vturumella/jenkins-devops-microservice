pipeline {
	agent any
	stages{
		stage('Build'){
			steps{
				echo'Build'	
			}
		}
		stage('test'){
			steps{
				echo 'Test'
			}
		}
		stages('Integration test'){
			steps{
				echo 'Integration Test'	
			}
		}
	}
}

