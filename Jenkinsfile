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
		stage('Integration test'){
			steps{
				echo 'Integration Test'	
			}
		}
	}
	post{
		always{
			echo 'I always rub'
		}
		success{
			echo " i run whem am successful"

		}
		failure{
			echo ' I run when i fail'
		}
	}
}

